MND YouTube Iframe API
======================
Wrapper for the YouTube Iframe API which simplifies event handling and provides responsiveness.

Dependencies
------------
None.

Examples
--------
```javascript
var player = new YouTubeIframePlayer('video-container', 'wRnSnfiUI54');

// Optional: overwrite this method like below if you wish to control when the player is inserted.
// By default the player will be inserted when the YouTube API is ready.
onYouTubeIframeAPIReady = function() {
  player.insertPlayer();
}

// Hook up to an event.
player.on('ended', function(data) {
  alert("Thanks for watching");
});
```

Events
------
All events forward the data from the YouTube API. The error event provides error code and message (data.code and data.message).

* ready
* error
* playbackRateChange
* playbackQualityChange
* apiChange
* unstarted
* ended
* playing
* paused
* buffering
* cued


Constructor arguments
---------------------
| Name                                                                  | Type    | Description                                         | Default value |
| ----                                                                  | ----    | -----------                                         | ------------- |
| playerContainerId                                                     | String  | The id of the element to be replaced by the iframe. | undefined     |
| videoId                                                               | String  | YouTube video id.                                   | undefined     |
| width                                                                 | Integer | Initial width.                                      | 560           |
| height                                                                | Integer | Initial height.                                     | 315           |
| [playerVars](https://developers.google.com/youtube/player_parameters) | Object  | Options for YouTube iframe.                         | {}            |
| responsiveIframe | Boolean | Adjust iframe size by parent container. | false |
| initialResize | Boolean | Initially adjust the iframe to its parent. | true |
| resizeTimeout                                                         | Integer | How long to wait between resizes.                   | 100           |

Developers
----------

You can run the tests on the console:
```
npm test
```

Or in your favorite web browser:
```
npm run open-tests
```
