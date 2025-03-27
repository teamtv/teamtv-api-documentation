# Sponsor

### List sponsors

**Request**

```javascript
sponsors = get(
   "https://api.teamtvsport.com/api/sponsors",
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
      "imageUrl" : "https://location/of/image-sponsor.png",
      "name" : "Some sponsor",
      "sponsorId" : "sp_95c9254d-91a4-4eb4-a434-123456789",
      "url" : "https://www.website-of-sponsor.com"
   },
   {
      "imageUrl" : "https://location/of/image-other-sponsor.png",
      "name" : "Some other sponsor",
      "sponsorId" : "sp_95c9254d-91a4-4eb4-a434-9128273",
      "url" : "https://www.website-of-other-sponsor.com"
   }
]
```


