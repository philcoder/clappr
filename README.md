# Clappr Player

[![Build Status](https://travis-ci.org/globocom/clappr.svg?branch=master)](https://travis-ci.org/globocom/clappr)
[![Dependency Status](https://gemnasium.com/globocom/clappr.svg)](https://gemnasium.com/globocom/clappr)
[![Pull Requests Stats](http://issuestats.com/github/globocom/clappr/badge/pr)](http://issuestats.com/github/globocom/clappr)
[![Issues Stats](http://issuestats.com/github/globocom/clappr/badge/issue)](http://issuestats.com/github/globocom/clappr)

<img src="https://i.cloudup.com/GSbXxvCsBK.png">


### Using the Player

Add the following script on your HTML:
```html
<head>
  <script type="text/javascript" src="http://cdn.clappr.io/latest/clappr.min.js"></script>
</head>
```
Now, create the player:
```html
<body>
  <div id="player"></div>
  <script>
    var player = new Clappr.Player({source: "http://your.video/here.mp4", parentId: "#player"});
  </script>
</body>
```

## Formats Supported

Format       |HLS|MP4|MP3|WEBM| [DASH](https://github.com/globocom/clappr/issues/161) | RTMP |
-------------|---|---|---|----|-------------------------------------------------------|------|
IE10         | ✔ | ✔ | ✔ |  ✘ | ✘ | ✔
IE11         | ✔ | ✔ | ✔ |  ✘ | ✘ | ✔
Firefox      | ✔ | ✔ | ✔ |  ✔ | ✘ | ✔
Chrome       | ✔ | ✔ | ✔ |  ✔ | ✘ | ✔
Safari       | ✔ | ✔ | ✔ |  ✘ | ✘ | ✔
iPhone       | ✔ | ✔ | ✔ |  ✘ | ✘ | ✘
iPad         | ✔ | ✔ | ✔ |  ✘ | ✘ | ✘
Android      | ✔ | ✔ | ✔ |  ✘ | ✘ | ✘
WiiU Browser | ✔ | ✔ | ✘ |  ? | ✘ | ✘
PS4 Browser  | ✔ | ✔ | ✘ |  ? | ✘ | ✘


## Built-in Plugins & Embed Parameters

All parameters listed below shall be added on `Clappr.Player` object instantiation. Example:
```javascript
var player = new Clappr.Player({
  source: "http://your.video/here.mp4",
  parameter1: "value1",
  parameter2: "value2",
});
```

##### Player Size
You can set the player size setting `width` and `height` parameters.

##### Auto Play
Add `autoPlay: true` if you want the video to automatic play after page load.

##### Auto Play when Visible
If you want to play the video when it appears partially on screen, set `autoPlayVisible: 'partial'`. In case you want the player to play when it is full visible, `autoPlayVisible: 'full'`.

##### Mute
Add `mute: true` if you want to start player with no sound.

##### Configuration persistance
Add `persistConfig: false` if you don't want to persist player's volume through your videos, by **default it saves**. These configuration are being saved at user's browser ([through localStorage](http://diveintohtml5.info/storage.html)).

##### Preload
In case you're loading a on demand video (mp4), it's possible to define the way the video will be preloaded according to [preload](http://www.stevesouders.com/blog/2013/04/12/html5-video-preload/) attribute options. Add `preload: <type>` on embed parameters. By default, Clappr will try to download only video metadata (`preload: 'metadata'`).

##### Google Analytics Plugin
Enable Google Analytics events dispatch (play/pause/stop/buffering/etc) adding your `gaAccount`. Optionally, pass your favorite trackerName as `gaTrackerName`. Example:

```javascript
  var player = new Clappr.Player({
    source: "http://your.video/here.mp4",
		gaAccount: 'UA-44332211-1',
		gaTracker: 'MyPlayerInstance'
  });
```

##### Control bar colors
Customize control bar colors adding `mediacontrol` hash. Example:

```javascript
  var player = new Clappr.Player({
    source: "http://your.video/here.mp4",
    mediacontrol: {seekbar: "#E113D3", buttons: "#66B2FF"}
  });
```
Result:

![Clappr with modified media control colors](https://s3.amazonaws.com/cdn.clappr.io/screenshot.png)

I'm sure you can do better than me.

##### Media Control Auto Hide

If you want to disable media control auto hide, add `hideMediaControl: false` in your embed parameters.

##### Watermark
Put `watermark: http://url/img.png` on your embed parameters to automatically add watermark on your video. Choose corner position by defining position parameter. Positions can be `bottom-left`, `bottom-right`, `top-left` and `top-right`. Example:

```javascript
  var player = new Clappr.Player({
    source: "http://your.video/here.mp4",
    watermark: "http://url/img.png", position: 'top-right'
  });
```

##### Poster
Define a poster by adding `poster: http://url/img.png` on your embed parameters. It will appear after video embed, disappear on play and go back when user stops the video.

##### Stats
Clappr has a native statistics plugin that accounts QoE metrics such playing time, rebuffering time, total rebuffers, etc. Metrics report happens periodically, learn how to access these numbers on [Create your own plugin](https://github.com/globocom/generator-clappr-plugin) session.


### Status

Clappr is under heavy development but production-ready. Feel free to open issues and send us pull requests.

### Installing for development

Clone the project and install gulp:

`npm install -g gulp`

Then enter the project directory and install the dependencies:

`npm install`

Make your changes and run the tests:

`npm test`

Build your own version:

`gulp build`

Check the result on `dist/` folder.

### Contributors

The culprits of this project are listed [here](https://github.com/globocom/clappr/graphs/contributors).

### Contributing

In general, we follow the fork-and-pull git workflow:

1. Fork the repository on GitHub
2. Commit changes to a branch in your fork
3. Pull request "upstream" with your changes
4. Merge changes in to "upstream" repository

:warning: Be sure to merge the latest from "upstream" before making a pull request.
