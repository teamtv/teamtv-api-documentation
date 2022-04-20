
# ResourceGroup

When working with resource within the TeamTV platform you always need a `ResourceGroup`. The `ResourceGroup` holds all resources together for a certain group, like a Team. The `ResourceGroup` also has a policy about the permissions per role. 

Each request to the TeamTV API **must** contain a the `X-Resource-Group-ID` header to tell TeamTV in which group you want to run your request.


## Create

**Request**
```javascript
resourceGroup = post(
   "https://api.teamtvsport.com/api/resourceGroups",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": clubResourceGroupId
   },
   body={
      "name": "PSV A2",
      "type": "team"
   }
)
```

**Response**
```json
{
  "tenantId": "nl_soccer_fcbalophetdak",
  "resourceGroupId": "45aaaaa-27f1-11eb-aaaa-123123123",
  "name": "FC Bal op het dak 1",
  "targetResourceName": "FC Bal op het dak 1",
  "targetResourceId": "team:aaaaaaa-27f1-11eb-aa12-bbbbfbaaf",
  "memberCount": 1,
  "created": "2021-08-20T11:59:44.726094Z",
  "updated": "2021-08-20T11:59:44.869725Z"
}
```

The `resourceGroupId` field in the returned `resourceGroup` object is the `teamResourceGroupId`. You need to keep a copy for further usage.


## List


**Request**

```javascript
resourceGroup = get(
   "https://api.teamtvsport.com/api/resourceGroups",
   headers={
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": clubResourceGroupId
   }
)
```

**Response**
```json
[
  {
    "tenantId": "nl_soccer_fcbalophetdak",
    "resourceGroupId": "45aaaaa-27f1-11eb-aaaa-123123123",
    "name": "FC Bal op het dak 1",
    "targetResourceName": "FC Bal op het dak 1",
    "targetResourceId": "team:aaaaaaa-27f1-11eb-aa12-bbbbfbaaf",
    "memberCount": 4,
    "created": "2020-11-16T09:51:16.731637Z",
    "updated": "2021-05-18T08:15:25.564400Z"
  },
  {
    "tenantId": "nl_soccer_fcbalophetdak",
    "resourceGroupId": "45aaaaa-27f1-11eb-8ff7-222123123",
    "name": "FC Bal op het dak 2",
    "targetResourceName": "FC Bal op het dak 2",
    "targetResourceId": "team:aaaaaaa-27f1-11eb-aa12-feedaaaa",
    "memberCount": 6,
    "created": "2020-11-16T09:52:54.545636Z",
    "updated": "2021-06-02T14:45:48.951428Z"
  }
]
```


