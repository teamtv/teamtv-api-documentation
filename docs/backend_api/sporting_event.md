# SportingEvent

### Create new SportingEvent
```javascript
sportingEvent = post(
   "https://api.teamtvsport.com/api/sportingEvents",
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
      "name": "home team - away team",
      "type": "match",
      "scheduledAt": "2020-06-12T13:31:56.735Z" 
   }
)
```
The `sportingEventId` field in the returned `sportingEvent` object is required for further actions with this entity (like uploading, playing video, etc). You need to keep a copy for further usage.

### Add One-time LivestreamEvent to SportingEvent

```javascript
livestreamEvent = post(
   `https://api.teamtvsport.com/api/sportingEvents/${sportingEventId}/createLivestreamEvent`,
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={
      "scheduledAt": "now",
      "broadcastToYoutube": false
   }
)

```
Options for `scheduledAt`:

- `"now"`: this will start the ingestion server right away
- `"YYYY-MM-DDTHH:mm:ss.sssZ"`: ingestion scheduled at `YYYY-MM-DDTHH:mm:ss.sssZ`
- default value: same as `sportingEvent.scheduledAt`

When `broadcastToYoutube` is set to `true` (default `false`) a youtube event will be created. `destinations[1].cdn_info.broadcast_id` in the response contains the youtube video id. 


**Response**
```json
{
   "livestreamEventId": "11111111-2222-3333-4444-555555555",
   "videoStreamInputs" : [
      {
        ....
         "streamingKey" : "66b0ac24-e221-11ea-9b8c-1a2c9e2082da",
         "streamingUrl" : "rtmp://ingest-livestreaming.teamtv.app/live"
        ....
      }
   ],
   .....
}

```



### Stopping a livestream

The default behaviour of a livestream is that it will end after 30 minutes of inactivity (not receiving data). When the livestream is ended the upload of the video to the platform is started.
In case you would like to trigger the upload before the 30 minutes delay, you can manually stop the livestream and trigger the upload.

```javascript
post(
   `https://api.teamtvsport.com/livestreaming/livestreamEvents/${livestreamEventId}/stop`,
   headers={
      "Content-Type": "application/json",
      "Authorization": `Bearer ${API_TOKEN}`,
      "X-Resource-Group-Id": teamResourceGroupId
   },
   body={}
)
```

