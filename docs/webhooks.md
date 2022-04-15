# Webhooks

When the webhook is installed, it will be called whenever an event occurred. 

Some details about the HTTP request (or HTTPS depending on your webhook url):

1. We send a POST request with the body encoded as json, and a `Content-Type: json` header
2. We don't send any authentication / signature
3. We don't look at the response code
4. We don't retry failed requests (because of 3)

If this is a problem feel free to reach out.

## SportingEvent.VideoAdded

The VideoAdded event is triggered when an upload is initialized. This means a new video entity is added to a SportingEvent, and the client can start uploading the files.
```javascript
{
  "eventName": "SportingEvent.VideoAdded",
  "data": {
    "tenantId": "nl_soccer_fc_bal_op_het_dak",
    "sportingEventId": "02ba96a8-7424-4ba3-877b-2f5533b305ed",
    "videoId": "200909fdbe8267"
  }
}
```

## Video.Uploaded

The VideoUploaded event is triggered when all files are successfully uploaded to teamtv. When this event happens the files are queued for encoding.

```javascript
{
  "eventName": "Video.Uploaded",
  "data": {
    "tenantId": "nl_soccer_fc_bal_op_het_dak",
    "sportingEventId": "02ba96a8-7424-4ba3-877b-2f5533b305ed",
    "videoId": "200909fdbe8267"
  }
}
```


## Video.Ready

The files are successfully encoded and the video is ready for usage.

```javascript
{
  "eventName": "Video.Ready",
  "data": {
    "tenantId": "nl_soccer_fc_bal_op_het_dak",
    "sportingEventId": "02ba96a8-7424-4ba3-877b-2f5533b305ed",
    "videoId": "200909fdbe8267"
  }   
}
```

