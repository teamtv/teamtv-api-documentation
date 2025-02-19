# Team

### Create new Team

**Request**

```javascript
team = post(
   "https://api.teamtvsport.com/api/teams",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
      "name": "HomeClub H1",
      "sportType": "hockey",
      "tags": {
        "someTag": "information-you-like"
      }
    }
)
```

**Response**

```json
{
    "teamId": "5a48a57c-eed3-11ef-9c14-aaaaaaaaaaaa",
    "name": "HomeClub H1",
    "shortCode": "EYE",
    "sportType": "hockey",
    "createdAt": "2025-02-19T15:08:19.199584Z",
    "tags": {
      "someTag": "information-you-like"
    }
}
```


### List

**Request**


```javascript
teams = get(
   "https://api.teamtvsport.com/api/teams",
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
        "teamId": "5a48a57c-eed3-11ef-9c14-aaaaaaaaaaaa",
        "name": "Eyedle H1",
        "shortCode": "EYE",
        "sportType": "hockey",
        "createdAt": "2025-02-19T15:08:19.199584Z",
        "tags": {
          "someTag": "information-you-like"
        }
    }
]
```
