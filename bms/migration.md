create migration in walrus.apart.data project
```
EntityFrameworkCore\Add-Migration extraCostUnits -context ApplicationDbContext

```

update database
```
EntityFrameworkCore\update-database -context ApplicationDbContext
```
update production  database
```
EntityFrameworkCore\update-database -context ApplicationDbContext --environment Production
```


{
  "name": "string",
  "location": "36.289302138924924 59.523817337654464",
  "geoLocation": {
    "x": 36.289302138924924,
    "y": 59.523817337654464
  },
  "address": "sssssssssss",
  "direction": "East",
  "unitsCount": 1,
  "meterage": 150,
  "cityId": "fa5a3305-6ed8-ee11-b74c-d6119150b969",
  "provinceId": "db5a3305-6ed8-ee11-b74c-d6119150b969",
  "hasRamp": true,
  "constructionYear": "1402",
  "hasElevator": true,
  "elevatorsCount": 1,
  "hasLobby": true,
  "usage": "commercial"
}