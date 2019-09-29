## Play next episode

This feature is for playlist videos。

### Open Option

if you want to open this feature，you have two way to open it.

#### first way

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

you add this line, the next episode button will show.

#### second way (recommend)

if you wang to dynamic control button show or hide，i recommend you choose this way.
i add to function to control button.

```javascript
dp.showNextEpisodeButton();
```

```javascript
dp.hideNextEpisodeButton();
```

use this way you can at anywhere to control you button.

### Event binding

after you open option, when you click the button, it will trigger a event `change_next_episode`.

you can at your code file to response event, like this

```javascript
dp.on('change_next_episode', function() {
    // TODO change video or do what you want
});
```
