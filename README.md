# Jekyll Embed Video

Embed YouTube, Vimeo, Twitch, and more in Jekyll webpages without a plugin. If you're hosting your webpage using GitHub pages only [whitelisted plugins](https://pages.github.com/versions/) are allowed. Here's a method using a Liquid template stored in `_includes` instead.

Fork of [this great project](https://github.com/nathancy/jekyll-embed-video) by [Nathan Lam](https://www.nathan-lam.com), rewritten to use a single template rather than one per-service. Both projects are released under the [MIT License](LICENSE.md).

## Table of Contents

* [Setup](#setup)
* [Usage](#usage)
  * [20DETIK](#20detik)
  * [Dailymotion](#dailymotion)
  * [Google Drive](#google-drive)
  * [Streamable](#streamable)
  * [Skynet](#skynet)
  * [Twitch](#twitch)
  * [Vidio](#vidio)
  * [Vimeo](#vimeo)
  * [YouTube](#youtube)
* [Responsive Videos](#responsive-videos)
* [Setting Variables](#setting-variables)

## Setup

Download [video-embed.html](_includes/video-embed.html) and place it in your `_includes` folder. That's it! No plugins, no datafiles.

## Usage

To embed video `VideoID` from `SiteName` in a Jekyll webpage, use the snippet

```liquid
{% include video-embed.html site="SiteName" id="VideoID" alt="Title" %}
```

in any markdown file. While technically optional, it's good practice to can replace `Title` with fallback text (usually the video's title) to appear should the `<iframe>` fail.

See below for example usage for each service and how to find the `VideoID` and [checkout this page](https://foggalong.github.io/jekyll-embed-video) for a full working demo.

### 20DETIK

Use `20DETIK` as `SiteName` and the number in the embedded video URL as the `VideoID` (for example, [20.detik.com/embed/190130051](https://20.detik.com/embed/190130051) would be `190130051`).

### Dailymotion

Use `Dailymotion` as `SiteName` and the ID in the video URL as the `VideoID` (for example, [dailymotion.com/video/x8429i4](https://dailymotion.com/video/x8429i4) would be `x8429i4`).

### Google Drive

We **strongly recommend** you upload your your video to [YouTube](#youtube) since it has better built in video player functionality. If you do still wish to use Google Drive though here are the steps:

1. Use `"Google Drive"` as the `SiteName`.

2. For the desired video, change the link sharing setting to '_On - Anyone with the link_'. This will make the video accessible to anyone who has the link as no sign-in is required. **If you do not change the video setting to this option, your video will not show**.
  
3. Now you need to find your ID. In Google Drive, double click the video to show the preview, click the setting options, and select '_Open in new window_'. Now click on the setting option again and select '_Embed item_'. **Right clicking the video will not bring up the embed option.** You must open the video in a new window.

4. This should display some `<iframe>` code. If, for example, your code was

   ```html
   <iframe src="https://drive.google.com/file/d/1EC8BnjJMon-vqy-UhLKk9sf_oukZzEbP/preview"></iframe>
   ```

   then your `VideoID` is `1EC8BnjJMon-vqy-UhLKk9sf_oukZzEbP/preview` would be your video ID.

Again, would highly recommend just using a unlisted [YouTube](#youtube) video instead.

### Skynet

Use `Skynet` as `SiteName` and the ID in the video URL as the `VideoID` (for example, [siasky.net/putIDHere](https://siasky.net/putIDHere) would be `putIDHere`). Note without an account, videos uploaded to Skynet are only saved for 90 days.

### Streamable

Use `Streamable` as `SiteName` and the ID in the URL as the `VideoID` (for example, [streamable.com/s9ijg](https://streamable.com/s9ijg) would be `s9ijg`). You can also use [Streamable's free online tool](https://streamable.com/embed-video).

### Twitch

Use `Twitch` as `SiteName` and the long string which appears in the URL as the `VideoID`. For example, [clips.twitch.tv/StylishChillyTubersDancingBaby](https://clips.twitch.tv/StylishChillyTubersDancingBaby) would be `StylishChillyTubersDancingBaby`.

For security purposes Twitch also asks for the URL on which the website is being embedded, but provided you’ve defined `site.url` as standard in your `_config.yml` then the template will [handle that](/_includes/video-embed.html#L61-L70). See the [embedding Twitch clips documentation](https://dev.twitch.tv/docs/embed/video-and-clips/#non-interactive-iframes-for-clips) for more details.

### Vidio

Use `Vidio` as `SiteName` and the number in the URL as the `VideoID`. For example, [vidio.com/watch/1671743-love-nature-channel-channel-trailer](https://vidio.com/watch/1671743-love-nature-channel-channel-trailer) would be `1671743`.

### Vimeo

Use `Vimeo` as `SiteName` and the number in the URL as the `VideoID` (for example, [vimeo.com/22439234](https://vimeo.com/22439234) would be `22439234`). Take a look at [accessing and editing embed codes](https://vimeo.zendesk.com/hc/articles/360000710167-Accessing-and-editing-embed-codes) if you're having trouble with your video's embed code ID.

### YouTube

Use `YouTube` as `SiteName` and `v` value in the URL as the `VideoID` (for example, [youtube.com/watch?v=T1itpPvFWHI](https://youtube.com/watch?v=T1itpPvFWHI) would be `T1itpPvFWHI`).

## Responsive Videos

The template includes [this CSS](_includes/video-embed.html#L41-L58) to make the videos fully responsive, automatically resizing with changing window sizes. If you'd prefer not to have this or want it included in another stylesheet then simply remove the contents of `<style> ... </style>` from the template.

## Setting Variables

The template includes several default variables, any number of which can be changed to suite your needs. This can be done globally by modifying the template or on a per-usage basis by passing as a parameter to the template.

Name         | Type    | Default | Description
:----------- | :------ | :------ | :----------
`autoplay`   | boolean | `false` | Determines if the video starts playing without the user clicking play. The exception is mobile devices, on which video cannot be played without user interaction.
`fullscreen` | boolean | `true`  | Determines if the player can go fullscreen.
`width`      | integer | `500px` | Width of the embedded window, in pixels.
`height`     | integer | `281px` | Height of the embedded window, in pixels.

There are three additional [`<iframe>` attributes](https://developer.mozilla.org/docs/Web/HTML/Element/iframe) which aren't (yet) exposed in this template but could be changed globally by modifying the template.

Name        | Type    | Default  | Description
:---------- | :------ | :------- | :----------
`scrolling` | boolean | `no`     | Indicates when the browser should provide a scroll bar (or other scrolling device) for the frame.
`muted`     | boolean | `false`  | Specifies whether the initial state of the video is muted.
`time`      | 1h2m3s  | `0h0m0s` | Time in the video where playback starts, given in hours, minutes, and seconds.
