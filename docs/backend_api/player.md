# Player

When a Person is attached to a Team it will become a Player. A Player object also holds information about the jersey number.

### Add a Person to a Team

**Request**

```javascript
player = post(
   "https://api.teamtvsport.com/api/teams/5a48a57c-eed3-11ef-9c14-aaaaaaaaaaaa/players",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
      "personId": "02cf6456-eed4-11ef-8ee7-aaaaaaaaaaaa",
      "number": "1337",
      "position": "CB
    }
)
```

**Response**

```json
{
    "personId": "02cf6456-eed4-11ef-8ee7-7fd8779489a4",
    "position": "CB",
    "number": "1337"
}
```

### List

**Request**

```javascript
players = get(
   "https://api.teamtvsport.com/api/teams/5a48a57c-eed3-11ef-9c14-aaaaaaaaaaaa/players",
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
        "personId": "02cf6456-eed4-11ef-8ee7-aaaaaaaaaaaa",
        "person": {
            "id": "02cf6456-eed4-11ef-8ee7-aaaaaaaaaaaa",
            "personId": "02cf6456-eed4-11ef-8ee7-aaaaaaaaaaaa",
            "firstName": "John",
            "lastName": "Doe",
            "fullName": "John Doe",
            "gender": "male",
            "teamId": "5ab26ae8-eed3-11ef-8123-aaaaaaaaaaaa"
        },
        "position": "CB",
        "number": "1337",
        "teamId": "5ab26ae8-eed3-11ef-8123-aaaaaaaaaaaa"
    }
]
```