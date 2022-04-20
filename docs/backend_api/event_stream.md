# EventStream

EventStreams provide an easy way to receive real-time enriched event data from livetagging. A stream can be provisioned per SportingEvent and is automatically backfilled with data entered before creation of the EventStream

## Provision an EventStream

Provision an EventStream and backfill it with data.

Keep in mind the `eventStreamId` and the id in the endpointUrls are *NOT* the same. You should always use the endpointUrls.

**Request**

```javascript
eventStream = post(
   `https://api.teamtvsport.com/api/sportingEvents/${sportingEventId}/eventStreams`,
   headers={
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   }
)
``` 


**Response**
```json
{
  "eventStreamId": "11111-22222-33333-4444-555555555",
  "endpointUrls": {
    "sse": "https:\/\/eventstream.teamtv.nl\/streams\/aaaa-bbbb-cccc-ddddd-eeeeeeee\/subscribe\/sse",
    "polling": "https:\/\/eventstream.teamtv.nl\/streams\/aaaa-bbbb-cccc-ddddd-eeeeeeee\/list"
  },
  "streamType": "all"
}
```


## List EventStreams



**Request**

```javascript
eventStreams = get(
   `https://api.teamtvsport.com/api/sportingEvents/${sportingEventId}/eventStreams`,
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
    "eventStreamId": "11111-22222-33333-4444-555555555",
    "endpointUrls": {
      "sse": "https:\/\/eventstream.teamtv.nl\/streams\/aaaa-bbbb-cccc-ddddd-eeeeeeee\/subscribe\/sse",
      "polling": "https:\/\/eventstream.teamtv.nl\/streams\/aaaa-bbbb-cccc-ddddd-eeeeeeee\/list"
    },
    "streamType": "all"
  }
]
```