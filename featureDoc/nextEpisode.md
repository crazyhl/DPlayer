## Play next episode

This feature is for playlist videos。

if you want to open this feature，you have two way to open it.

#### First

you can at init function add option, like this:

```diff
const dp = new DPlayer({
    container: document.getElementById("dplayer"),
    autoplay: true,
    video: {
        url: url,
        type: "hls",
    },
+   nextEpisode: true,
    contextmenu: [
        {
            text: '上一集',
            click: (player) => {
                let url = getPreVideo();
                changeVideo(player, url);
            },
        },
        {
            text: '下一集',
            click: (player) => {
                let url = getNextVideo();
                changeVideo(player, url);
            },
        },
    ],
});
```
