# Person

### Create new Person

**Request**

```javascript
team = post(
   "https://api.teamtvsport.com/api/persons",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
        "firstName":"John",
        "lastName":"Doe",
        "gender":"male",
        "tags": {
            "additional-info": "can be stored here"
        }
   }
)
```

**Response**

```json
{
    "personId": "02cf6456-eed4-11ef-8ee7-aaaaaaaaaaaa",
    "firstName": "John",
    "lastName": "Doe",
    "gender": "male",
    "tags": {
        "additional-info": "can be stored here"
    },
    "createdAt": "2025-02-19T15:13:01.939886Z"
}
```


### List 

**Request**


```javascript
teams = get(
   "https://api.teamtvsport.com/api/persons",
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
        "firstName": "John",
        "lastName": "Doe",
        "gender": "male",
        "tags": {
            "additional-info": "can be stored here"
        },
        "createdAt": "2025-02-19T15:13:01.939886Z"
    }
]
```


