# Scritch player

![logo](https://imgur.com/uHFIa0q.png)

Scritch player is a simple HTML media player designed for ease of creation and customization. If you have a collection of audio files, simply drop them in and upload to a website to get a player to listen to it!

The original intention was to create a media player for musicians to use to upload their albums to [itch.io](https://itch.io). Something for them to easily copy/migrate their existing albums from sites like bandcamp.

## How to

### Scritch editor

The [Scritch editor](https://torcado.itch.io/scritch-editor) is a tool made to streamline this process. You can use it to create a Scritch player right in your browser, and see customization changes immediately.

Otherwise, manually setting up the player is just as easy.

### Manual

1. Place audio files and cover art in the /media folder

2. Edit `config.json` to include the audio files. Add entries to the `media` array like so:

```json
"media": [
    {
        "file": "track1.mp3",
        "title": "Track 1",
        "info": "(lyrics or other information can go here)",
        "feature": true
    },
    {
        "file": "track2.mp3",
        "title": "Track 2",
    },
    ...
]
```

3. Set the cover art file in `config.json`:

```json
"cover": "cover.png"
```

4. (optional) Add a title to `config.json`, like so:

```json
"title": "My Album"
```

5. (optional) Add a description to `config.json`, like so:

```json
"description": "(add text here)"
```

6. (optional) Edit `config.json` to modify the player's theme to your liking:

```json
"theme": {
    "coverSize": 480,
    "layoutStyle": "horizontal",
    "infoStyle": "overlaid",
    "titleStyle": "span",
    "contentWidth": 400,
    "nativePlayer": false
},
```

And that's it! you can upload the files to your website, or zip them up and upload to [itch.io](https://itch.io), or anywhere else that can host HTML projects.


### config.json settings

*note: all display-text options can include HTML, not just plain text*

`title` (optional)
> Text at the top of the player  
> `"title": "My Album"`  
  
\
`media`
> List of media files to include in the player  
> ```json
> "media": [
>     {"file": "track1.mp3", "title": "Track 1"},
>     ...
> ]
> ```

\
`cover` (optional)  
> The name of the file in the /media folder for the cover image  

\
`description` (optional)  
> The text at the bottom of the player  

\
`theme` (optional)  
> An object containing theme settings and colors  

-----

**media entry options**  

`file`  
> The name of the file in the /media folder  

\
`title` (optional)  
> The name shown for this entry in the player.  
> Defaults to the file name if not specified  

\
`featured` (optional)  
> If `true`, sets this file as the "featured" track, which will queue up first when loading the page.  
> Can be either `true` or `false`  

\
`type` (optional)  
> The type of the media.  
> Can be either `"audio"` or `"video"`  
> Defaults to "audio"  

\
`info` (optional)  
> Extra text for this file, such as for lyrics or artist attributions. This will be optionally shown over/under the cover image, or togglable below the track.  

-----

**theme options**  

*all settings are optional. colors can be any valid CSS color*

`titleStyle`  
> Styles the title text, if available.  
> `"none"` (default) no styling  
> `"span"` title spans the entire width, centered.  

\
`backgroundColor`  
> Color of the page background  

\
`primaryColor`  
> Main color of the controls (e.g. the circle of the play button, the prev/next track buttons, the filled progress bar, etc.)  

\
`primaryAltColor`  
> Color of e.g. the unfilled section of the progress bar and volume bar  

\
`secondaryColor`  
> Secondary color of the controls (e.g. the triangle of the play button)  

\
`highlightColor`  
> Background color of the selected track  

\
`primaryTextColor`  
> Color of most text (e.g. titles, description, info, etc.)  

\
`primaryAltTextColor`  
> Color of e.g. the track numbers and duration, and the track info button  

\
`linkColor`  
> Color of links in text  

\
`layoutStyle`  
> Styles the overall structure of the player  
> `"horizontal"` (default) the cover image sits to the right of the player controls and track list  
> `"vertical"` all elements align vertically (from top to bottom: title -> cover -> controls -> track list)  

\
`infoStyle`  
> Styles the track info of the currently playing track  
> `"overlaid"` (default) text sits layered on top of the cover image  
> `"below"` text sits below the cover image (note: this will push down the controls and track list in a vertical layout)  

\
`contentWidth`  
> Width of the column containing the controls, track list, and description  

\
`coverSize`  
> Width of the cover image (non-square images will scale accordingly)  

\
`nativePlayer`  
> Changes the player controls  
> `false` (default) custom player controls  
> `true` uses the browser's default audio player (also hides the player when a video is playing, the video's default controls will be available)  

\
`customCSS`  
> Custom changes to the page's CSS  