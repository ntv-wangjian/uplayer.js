# uplayer.js
A very simple and powerful HTML 5 web Player,Which can playback H264/H265 video and aac audio transported in http(s) or WebSocket.

## Overview
uplayer.js works by transmuxing TS、FLV、MP4 stream into ISO BMFF (Fragmented MP4) segments, followed by feeding mp4 segments into an HTML5 `<video>` element through [Media Source Extensions][] API.
[Media Source Extensions]: https://w3c.github.io/media-source/

## Demo and Media Server
[uplayer demo](http://player.ruiboyun.cn/)
[Media Server](http://www.ruiboyun.com/)
## Features
- Playback livestream and vod stream
- Playback for HLS stream with H.264/H.265 + AAC codec transported in http(s) or WebSocket
- Playback for FLV stream with H.264/H.265 + AAC codec transported in http(s) or WebSocket
- Extremely low latency of less than 1 second in the best case
- Support Chrome, FireFox, Safari, Edge (Old or Chromium) or any Chromium-based browsers
- Support chasing latency automatically for internal buffer of HTMLMediaElement
- Low CPU overhead and low memory usage (JS heap takes about 10MiB for each instance)
- Multi player instance in one web page

## Getting Started
```html
<script type="text/javascript" src="uplayer.min.js"></script>
<div id="video_div" style="width: 640px;width: 320px;"></div>
<script type="text/javascript">
    /**
     * play(url,divId,format)
     * @param {string} url    
     * @param {string} divId  html element id 
     * @param {string} format can be flv, hls, rtmp, mp4, can be omitted
    */
    var divId  = "video_div";
    var format = "";
    var url    = "your-video-url";
    if(url!=""){
         stopAll();
         play(url,divId,format);
    }
</script>
```

## Limitations
- G711 audio codec is not support
- MP3 audio codec is currently not working on IE11 / Edge
- HTTP FLV live stream is not currently working on all browsers

