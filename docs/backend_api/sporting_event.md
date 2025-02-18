# SportingEvent

### Create new SportingEvent

**Request**

```javascript
sportingEvent = post(
   "https://api.teamtvsport.com/api/sportingEvents",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
      "name": "HomeClub H1 - AwayClub H1",
      "scheduledAt": "2025-02-18T10:55:54.330Z",
      "sportType": "hockey",
      "homeTeamId": "e54b1dd2-ede6-11ef-998c-aaaaaaaaaaaa",
      "awayTeamId": "b01e42a0-ede7-11ef-a2d7-aaaaaaaeaaaa",
      "type": "match",
      "tags": {
        "matchConfig": {
          "periodCount": 2,
          "firstPeriodPlayingDirection": "HOME_AWAY"
        },
        "automaticCameraConfig": {
          "record": false
        }
      },
    }
)
```

**Response**

```json
{
  "sportingEventId": "b05b488a-ede7-11ef-a8db-aaaaaaaaaaaa",
  "sportingEventTRN": "trn:sport:sportingevent:b05b488a-ede7-11ef-a8db-aaaaaaaaaaaa",
  "observationLogId": "b05b4b46-ede7-11ef-9903-aaaaaaaaaaaa",
  "name": "HomeClub H1 - AwayClub H1",
  "createdAt": "2025-02-18T11:01:22.528296Z",
  "scheduledAt": "2025-02-18T10:55:54.330000Z",
  "videoIds": [],
  "clocks": {
    "live": {
      "clockId": "U1",
      "synchronizationPoints": []
    }
  },
  "tags": {
    "matchConfig": {
      "periodCount": 2,
      "firstPeriodPlayingDirection": "HOME_AWAY"
    },
    "automaticCameraConfig": {
      "record": false
    }
  },
  "type": "match",
  "homeTeamId": "e54b1dd2-ede6-11ef-998c-aaaaaaaaaaaa",
  "awayTeamId": "b01e42a0-ede7-11ef-a2d7-aaaaaaaeaaaa",
  "lineUpId": "b06cdbcc-ede7-11ef-b15e-aaaaaaaaaaaa"
}
```


The `sportingEventId` field in the returned `sportingEvent` object is required for further actions with this entity (like uploading, playing video, etc). You need to keep a copy for further usage.

### List 

**Request**


```javascript
sportingEvents = get(
   "https://api.teamtvsport.com/api/sportingEvents",
   headers={
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   }
)
```

**Response**


```json
[
    {
      "sportingEventId": "b05b488a-ede7-11ef-a8db-aaaaaaaaaaaa",
      "sportingEventTRN": "trn:sport:sportingevent:b05b488a-ede7-11ef-a8db-aaaaaaaaaaaa",
      "observationLogId": "b05b4b46-ede7-11ef-9903-aaaaaaaaaaaa",
      "name": "HomeClub H1 - AwayClub H1",
      "createdAt": "2025-02-18T11:01:22.528296Z",
      "scheduledAt": "2025-02-18T10:55:54.330000Z",
      "videoIds": [],
      "clocks": {
        "live": {
          "clockId": "U1",
          "synchronizationPoints": []
        }
      },
      "tags": {
        "matchConfig": {
          "periodCount": 2,
          "firstPeriodPlayingDirection": "HOME_AWAY"
        },
        "automaticCameraConfig": {
          "record": false
        }
      },
      "type": "match",
      "homeTeamId": "e54b1dd2-ede6-11ef-998c-aaaaaaaaaaaa",
      "awayTeamId": "b01e42a0-ede7-11ef-a2d7-aaaaaaaeaaaa",
      "lineUpId": "b06cdbcc-ede7-11ef-b15e-aaaaaaaaaaaa"
    }
]
```


