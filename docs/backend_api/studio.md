# Studio

Get highlight videos

**Request**

```javascript
token = get(
   `https://api.teamtvsport.com/api/studio/highlightVideos`,
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": clubResourceGroupId
   }
)
```

**Response**
```json
[
   {
      "createdAt" : "2022-10-20T06:27:36.216502Z",
      "embedCode" : "<script src=\"https://cdn.jwplayer.com/players/dF60HNMO-IhwLzZyK.js\"></script>",
      "match" : {
         "awayTeam" : {
            "name" : "Racing Bruxelles H1",
            "teamId" : "ab027abc-2af9-4f50-b20d-1234567a"
         },
         "homeTeam" : {
            "name" : "Braxgata H1",
            "teamId" : "7f76cd68-27f1-11eb-81a1-1234567b"
         },
         "name" : "Braxgata H1 - Racing Bruxelles H1",
         "scheduledAt" : "2022-10-19T14:30:00.000000Z",
         "score" : {
            "away" : 0,
            "home" : 2
         },
         "sportingEventId" : "5a8e85d1-1b97-4c60-8b24-1234567c"
      },
      "publicationId" : "ad0a09fa-111d-440f-aae6-1234567d",
      "resourceGroupId" : "7f880fa6-27f1-11eb-8ff7-1234567c",
      "thumbnailUrl" : "https://cdn.jwplayer.com/thumbs/dF60HNMO-720.jpg",
      "title" : "PC's & Goals Braxgata H1 - Racing H1 2-0"
   }
]
```
