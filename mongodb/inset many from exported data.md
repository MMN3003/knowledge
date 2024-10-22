```js
function convertExtendedJSON(doc) {

// Check if the input is an array

if (Array.isArray(doc)) {

return doc.map(d => convertExtendedJSON(d)); // Recursively process each document in the array

}

  

// Loop through each field in the document

for (let key in doc) {

if (doc.hasOwnProperty(key)) {

// Check for $oid and convert to ObjectId

if (doc[key] && typeof doc[key] === 'object' && doc[key].$oid) {

doc[key] = ObjectId(doc[key].$oid);

}

  

// Check for $date and convert to new Date

else if (doc[key] && typeof doc[key] === 'object' && doc[key].$date) {

doc[key] = new Date(doc[key].$date);

}

  

// If the value is another object or array, recursively convert its fields

else if (typeof doc[key] === 'object') {

doc[key] = convertExtendedJSON(doc[key]);

}

}

}

  

return doc;

}

  

// Example usage:

let extendedJSONData = [{

"_id": {

"$oid": "65e7462426105f91c0843572"

},

"created_at": {

"$date": "2024-03-05T16:19:48.435Z"

},

"user_id": {

"$oid": "65c679ccbff07cc976db8ff8"

},

"logo_url": "https://d2wn6f04lhvy4g.cloudfront.net/users/avatars/65c679ccbff07cc976db8ff8/2024-03-05/459fff89-6b92-400c-9f8d-5949262f3ff0.jpeg",

"cover_url": "https://d2wn6f04lhvy4g.cloudfront.net/team/cover/65c679ccbff07cc976db8ff8/2024-03-05/01e7d194-c51b-4df3-b402-206d03b8a9bb.jpeg",

"colors": [

"#FF4BF9",

"#F22CD5",

"#E60EB3"

],

"name": "Joe Gibbs Racing ",

"description": "The Official Account of Joe Gibbs Racing. \nThe very best in NASCAR.\n\nhttps://joegibbsracing.com",

"info": "The Official Account of Joe Gibbs Racing. \nThe very best in NASCAR.\n\nhttps://joegibbsracing.com",

"rules": [],

"state": null,

"city": null,

"blue_checkmark": false,

"is_hidden": false,

"admins": [

{

"user_id": {

"$oid": "65c679ccbff07cc976db8ff8"

},

"position": "LEADER",

"_id": {

"$oid": "65e7462426105f91c0843573"

}

},

{

"user_id": {

"$oid": "65e8db09baa3f2131598eb61"

},

"position": "CO_LEADER",

"_id": {

"$oid": "65f7612bacf1db9765baa917"

}

},

{

"user_id": {

"$oid": "65f8a155acf1db9765bad91e"

},

"position": "CO_LEADER",

"_id": {

"$oid": "660a1f30d72806ed0a5bb54d"

}

},

{

"user_id": {

"$oid": "65c67cf0e06f27a1fe1c563a"

},

"position": "CO_LEADER",

"_id": {

"$oid": "669fbd4af8dada84df616df1"

}

},

{

"user_id": {

"$oid": "65c67a33ad672b6dfc63d4ac"

},

"position": "CO_LEADER",

"_id": {

"$oid": "6716923613f4eedc6d3fd025"

}

}

],

"site_url": null,

"email": null,

"social_links": {

"_id": {

"$oid": "660a2021d72806ed0a5bb905"

}

},

"__v": 0,

"updated_at": {

"$date": "2024-04-01T02:46:57.106Z"

}

}];

  

// Convert extended JSON to MongoDB shell-friendly format

let convertedData = convertExtendedJSON(extendedJSONData);

  

// Now you can insert the converted data into your MongoDB collection

let operations = convertedData.map(doc => {

return {

updateOne: {

filter: { _id: doc._id }, // Find by _id

update: { $set: doc }, // Update the document with new data

upsert: true // Insert if it doesn't exist

}

};

});

  

// Perform bulkWrite operation

db.teams.bulkWrite(operations, { ordered: false });
```