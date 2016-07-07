# player.plugin.selector-menu
A Bitrate selector menu

## Initialize 

```Javascript
var video = videojs("#id",{plugins:{selectorMenu: {}},function(){})
// or
video.selectorMenu()
```

## Set Bitrates

```Javascript
   player.trigger('menudataready', {
      menuData:[
      //stream example
        {
          id: 0,
          selected: true,
          label: "auto",
          src: "Some/Live/Stream/URL.m3u8",
          type: "application/x-mpegURL"
        },
        //vod example
        {
          id: 1,
          selected: false,
          label: "1080p",
          src: "Some/vod/URL.mp4",
          type: "video/mp4"
        },
        //audil example
        {
          id: 3,
          selected: false,
          label: "Audio Only",
          src: "Some/audio.mp3",
          type: "audio/mp3"
        }
        /*
        The menu will look like 
           [auto]
           [1080p]
         [Audio Only]
        */
      ],
      onChange: function () {
          console.log("bitrate "+this.label+" was clicked")
          player.src({ type: this.type, src: this.src });
      }
    });
```

## build 
$ ``` webpack ```
