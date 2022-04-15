# Tokens

With an admin API Token you can request new API tokens with limited access. Using the `createRoleToken` API you can request a new token providing access to a single `ResourceGroup` and a certain role. Tokens generated using this API are valid for 24 hours. 

```javascript
token = post(
   `https://ttv-platform.herokuapp.com/api/resourceGroups/${teamResourceGroupId}/createRoleToken`,
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": clubResourceGroupId
   },
   body={
      "roleName": "trainer" / "player" 
   }
)
```