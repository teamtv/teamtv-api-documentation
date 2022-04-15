# Embedding

TeamTV allows you to embed parts of the platform into your own application. 
The embed widget supports these components:

- Upload
- Video player (custom clips)

## Loading the script
To add the embed code to your page add the following script to your html. This will load our embed script for the cdn. By default this will add the `TeamTV` widget to `window`.
```html
<script src="https://embed.teamtv.dev/script.min.js?v=1"></script>
```

## Initializing
To initialize the widget you need to have a token. This token can be obtained using the [createRoleToken](/backend_api#tokens) API. When you initialize the iframe will be injected into your page and the embed page of TeamTV will get loaded. The iframe is hidden (`display: block`) by default.

```javascript
TeamTV.init(
  tokenFromBackend,
  {
    colors: {
      primary: '#ff00ff',
      secondary: '#00ff0f'
    }
  }
)
```

## Starting an upload
Once the widget is initialized you can trigger the upload dialog. You need the sportingEventId to be able to trigger the dialog. The sportingEventId is returned by the [SportingEvent API](/backend_api#sportingEvent).

```javascript

var options = {
  onClose: function () {
    console.debug("upload modal closed");
  },
};

TeamTV.uploadVideo(
  sportingEventId, 
  (eventName, {videoId}) => {
      switch (eventName)
      {
        case 'Started':
          console.log(`Upload started for ${videoId}`);
          break;
        case 'Uploaded':
          console.log(`Upload finished for ${videoId}`);
          break;
      }
  },
  options  
);
```

## Video player

```javascript
var options = {
  videoId: videoId,
  onClose: function () {
    console.debug("clips modal closed");
  },
};

TeamTV.showClips(
  sportingEventId,
  [
    {
      startTime: 100,
      endTime: 110,
      description: "Goal 1-0 Bayern"
    },
    {
      startTime: 200,
      endTime: 220,
      description: "Goal 1-1 Barcelona"
    }
  ],
  options
)
```

## Themes

This is work in progress. Will be added to [init](#initializing).


## Example

```html
<html>
<head>
<script src="https://embed.teamtv.dev/script.min.js?v=1"></script>
<script>
    function showClips() {
      TeamTV.showClips(
        // sportingEventId
        "c563d125-b68d-462d-9508-2d11c129c574",
        [
          {
            description: "Shot 1",
            startTime: 560,
            endTime: 570
          },
          {
            description: "Shot 2",
            startTime: 1000,
            endTime: 1020
          }
        ]
      )
    }
</script>
</head>
<body>
<button onclick="TeamTV.uploadVideo('8285661f-0b0c-47ca-b540-e8a7084cc3de')">upload</button>
<button onclick="showClips()">clips</button>

<script>
  TeamTV.init(
    "<get your token from the backend>",
    {
      colors: {
        primary: '#ff00ff',
        secondary: '#00ff0f'
      }
    }
  );
</script>
</body>
</html>

```