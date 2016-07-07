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
          label: "auto",
          src: "Some/vod/URL.mp4",
          type: "video/mp4"
        }
        
      ],
      onChange: function () {
          console.log("bitrate "+this.label+" was clicked")
          player.src({ type: this.type, src: this.src });
      }
    });
```

## build 
``` webpack ```
