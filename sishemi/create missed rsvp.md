``` js
db.communities.aggregate([

{

$lookup: {

from: "communitymembers",

localField: "_id",

foreignField: "community_id",

as: "community_members"

}

},

{

$addFields: {

member_count: { $size: "$community_members" }

}

},

{

$match: { member_count: { $gt: 0 } }

},

{

$lookup: {

from: "events",

localField: "_id",

foreignField: "team_community_id",

as: "event_details"

}

},

{ $unwind: "$event_details" },

{

$match: { "event_details.is_rsvp_enabled": true }

},

{

$lookup: {

from: "eventrsvps",

localField: "event_details._id",

foreignField: "event_id",

as: "rsvp_details"

}

},

{

$addFields: {

rsvp_count: { $size: "$rsvp_details" },

member_count: { $size: "$community_members" }

}

},

{

$match: {

rsvp_count: { $gt: 0 },

$expr: { $lt: ["$rsvp_count", "$member_count"] }

}

},

{

$addFields: {

community_member_ids: {

$map: { input: "$community_members", as: "member", in: "$$member.user_id" }

},

rsvp_user_ids: {

$map: { input: "$rsvp_details", as: "rsvp", in: "$$rsvp.user_id" }

}

}

},

{

$addFields: {

missing_rsvp_user_ids: {

$setDifference: ["$community_member_ids", "$rsvp_user_ids"]

}

}

},

{

$project: {

event_id: "$event_details._id",

event_end: "$event_details.end",

missing_rsvp_user_ids: 1

}

}

]).forEach(result => {

// console.log(result);

const { event_id,event_end, missing_rsvp_user_ids } = result;

// Step 2: Insert missing RSVPs

const bulkOps = missing_rsvp_user_ids.map(user_id => ({

insertOne: {

document: {

event_id: event_id,

user_id: user_id,

status: "NO_RESPONSE",

expires_at: new Date(event_end.getTime() + 1000 * 60 * 60 * 24*7)

}

}

}));

  

if (bulkOps.length > 0) {

db.eventrsvps.bulkWrite(bulkOps);

}

});
```