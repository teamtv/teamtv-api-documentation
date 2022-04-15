# Studio

Get highlight videos

**Request**

```javascript
token = get(
   `https://ttv-platform.herokuapp.com/api/studio/highlightVideos`,
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
      "embedCode" : "<iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/XhbdpjILa6U\" title=\"YouTube video player\" frameborder=\"0\" allow=\"accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe>",
      "title" : "Summary PSV 1 - Ajax 1",
      "resourceGroupId" : "8272-2223-aaaa-bbbbbcccccc-ffff",
      "highlightVideoId" : "aaaa-bbbb-cccc-ddddddddd-eeee",
      "scheduledAt" : "2021-07-04T19:30:0.000Z",
      "score" : {
         "home" : 3,
         "away" : 1
      },
      "teams" : {
         "away" : "Ajax 1",
         "home" : "PSV 1"
      },
      "type" : "summary",
      "createdAt" : "2021-07-05T10:00:18.123Z",
      "thumbnailUrl" : "https://i.ytimg.com/vi/Mynx_hExwJw/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCMgofrdTxL6TVnhMqvsOUfsKT5-g"
   },
   {
      "title" : "Summary PSV 2 - Oranje Rood 2",
      "embedCode" : "<iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/02uh5ZBXokg\" title=\"YouTube video player\" frameborder=\"0\" allow=\"accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe>",
      "scheduledAt" : "2021-08-04T19:30:0.000Z",
      "highlightVideoId" : "aaaa-bbbb-cccc-ddddddddd-eee1",
      "resourceGroupId" : "8272-2223-aaaa-bbbbbcccccc-fff1",
      "type" : "summary",
      "teams" : {
         "away" : "Oranje Rood 2",
         "home" : "PSV 2"
      },
      "score" : {
         "home" : 1,
         "away" : 1
      },
      "createdAt" : "2021-08-05T10:00:18.123Z",
      "thumbnailUrl" : "https://i.ytimg.com/vi/_wMUGAju9Ww/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLACNGK56gJz7GbQh1Nl_SSU7fVEcQ"
   }
]
```

Get livestreamEvents

**Request**
```javascript
token = get(
   `https://ttv-platform.herokuapp.com/api/studio/livestreamEvent`,
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
      "scheduledAt" : "2021-08-09T19:30:0.000Z",
      "score" : {
         "away" : 0,
         "home" : 0
      },
      "state" : "upcoming",
      "title" : "PSV 1 - Ajax 1",
      "teams" : {
         "home" : "PSV 1",
         "away" : "Ajax 1"
      },
      "embedCode" : "<iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/2CD9aEjFZwU\" title=\"YouTube video player\" frameborder=\"0\" allow=\"accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe>",
      "livestreamEventId" : "aaaa-bbbb-cccc-ddddddddd-eeee",
      "resourceGroupId" : "8272-2223-aaaa-bbbbbcccccc-ffff"
   },
   {
      "teams" : {
         "away" : "Ajax 2",
         "home" : "PSV 2"
      },
      "embedCode" : "<iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/I83XWCSBgSc\" title=\"YouTube video player\" frameborder=\"0\" allow=\"accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe>",
      "livestreamEventId" : "aaaa-bbbb-cccc-ddddddddd-eeee",
      "resourceGroupId" : "8272-2223-aaaa-bbbbbcccccc-fff1",
      "scheduledAt" : "2021-08-05T19:30:0.000Z",
      "score" : {
         "away" : 0,
         "home" : 1
      },
      "state" : "live",
      "title" : "PSV 2 - Ajax 2"
   }
]
```
