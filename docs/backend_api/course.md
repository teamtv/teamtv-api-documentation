# Course


### List all available courses within your tenant

**Request**

```javascript
courses = get(
   "https://api.teamtvsport.com/api/courses",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": tenantResourceGroupId
   }
)
```

**Response**

```json
[
  {
    "courseId": "korfbaltrainer-2",
    "name": "Korfbal trainer 2"
  },
  {
    "courseId": "korfbaltrainer-3",
    "name": "Korfbal Trainer 3"
  }
]
```

# LearningGroup

## Create a new `LearningGroup` for a certain `Course`

**Request**

```javascript
class = post(
   "https://api.teamtvsport.com/api/learningGroups",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": tenantResourceGroupId
   },
   body={
      "courseId": "korfbaltrainer-2",
      "name": "Korfbal Trainer 2 - 2022/2023 - Dalto",
      "trainees": [
        {
            "firstName": "Koen", 
            "lastName": "Vossen", 
            "email": "koen@teamtv.nl",
            "tags": {
                "refId": "NDH81P2"
            } 
        }
      ],
      "tags": {
        "mijnKorfbalId": "18237-123123-123-123"
      }
   }
)
```

**Response**

```json
{
  "learningGroupId": "cb25959c-c8b8-474a-a84b-5a409fda5519",
  "name": "Korfbal Trainer 2 - 2022/2023 - Dalto",
  "tags": {
    "mijnKorfbalId": "18237-123123-123-123"
  }
}
```

## Add a Trainee to an existing LearningGroup

**Request**

```javascript
trainee = post(
   "https://api.teamtvsport.com/api/learningGroups/cb25959c-c8b8-474a-a84b-5a409fda5519/trainees",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": tenantResourceGroupId
   },
   body={
        "firstName": "Koen", 
        "lastName": "Vossen", 
        "email": "koen@teamtv.nl",
        "tags": {
            "refId": "NDH81P2"
        } 
   }
)
```

**Response**

```json
{
    "firstName": "Koen", 
    "lastName": "Vossen", 
    "email": "koen@teamtv.nl",
    "tags": {
        "refId": "NDH81P2"
    } 
}
```




