---
title: Jekyll Embed Video Demo
---

[Jekyll Embed Video] allows you to easily embed a video into a Jekyll webpage without using plugins. It's based on this [template collection] by [Nathan Lam], but combines them into a [single template] for easier use. This page is **heavy** because it gives an example of the template in use for every service.

[Jekyll Embed Video]: https://github.com/Foggalong/jekyll-embed-video
[template collection]: https://github.com/nathancy/jekyll-embed-video
[Nathan Lam]: https://www.nathan-lam.com
[single template]: https://github.com/Foggalong/jekyll-embed-video/blob/main/_includes/video-embed.html

## 20DETIK

Here video IDs are just the URL number, e.g. [20.detik.com/embed/190130051][detik]

[detik]: https://20.detik.com/embed/190130051

{%- include video-embed.html site="20DETIK" id="190130051" alt="McGregor dan Khabib Resmi Dijatuhi Sanksi!" -%}

```liquid
{% raw %}{%- include video-embed.html site="20DETIK" id="190130051" alt="McGregor dan Khabib Resmi Dijatuhi Sanksi!" -%}{% endraw %}
```

## Dailymotion

Here video IDs are just the URL code, e.g. [dailymotion.com/video/x8429i4][dailymotion]

[dailymotion]: https://www.dailymotion.com/video/x8429i4

{%- include video-embed.html site="Dailymotion" id="x8429i4" alt="Former FBI Agent Breaks Down His Own Body Language" -%}

```liquid
{% raw %}{%- include video-embed.html site="Dailymotion" id="x8429i4" alt="Former FBI Agent Breaks Down His Own Body Language" -%}{% endraw %}
```

## Google Drive

Using Google Drive videos is a bit more complicated; [check the README][wiki] for instructions on how to make videos available and where to find the embed ID.

[wiki]: https://github.com/nathancy/jekyll-embed-video#embed-google-drive

{%- include video-embed.html site="Google Drive" id="0B7L_dMcaZknxVTRndmdSQ0F5OFE/preview" alt="Road Rage" -%}

```liquid
{% raw %}{%- include video-embed.html site="Google Drive" id="0B7L_dMcaZknxVTRndmdSQ0F5OFE/preview" alt="Road Rage" -%}{% endraw %}
```

## Streamable

Here video IDs are just in URL, e.g. [streamable.com/s9ijg][streamable]

[streamable]: https://streamable.com/s9ijg

{%- include video-embed.html site="Streamable" id="s9ijg" alt="Disguised Toast" -%}

```liquid
{% raw %}{%- include video-embed.html site="Streamable" id="s9ijg" alt="Disguised Toast" -%}{% endraw %}
```

## Twitch

For Twitch the video IDs are the long string which appears in the URL, e.g. [clips.twitch.tv/StylishChillyTubersDancingBaby][twitch]. For security purposes Twitch also asks for the URL on which the website is being embedded, but provided you've defined `site.url` as standard in your config the template will handle all that.

[twitch]: https://clips.twitch.tv/StylishChillyTubersDancingBaby

{%- include video-embed.html site="Twitch" id="StylishChillyTubersDancingBaby" alt="LCK Production" -%}

```liquid
{% raw %}{%- include video-embed.html site="Twitch" id="StylishChillyTubersDancingBaby" alt="LCK Production" -%}{% endraw %}
```

## Vidio

Here video IDs are just the URL number, e.g. [vidio.com/watch/1671743-love-nature-channel-channel-trailer][vidio].

[vidio]: https://vidio.com/watch/1671743-love-nature-channel-channel-trailer

{% include video-embed.html site="Vidio" id="1671743" alt="Love Nature Channel Trailer" %}

```liquid
{% raw %}{% include video-embed.html site="Vidio" id="1671743" alt="Love Nature Channel Trailer" %}{% endraw %}
```

## Vimeo

Here video IDs are just the URL number, e.g. [vimeo.com/22439234][vimeo].

[vimeo]: https://vimeo.com/22439234

{% include video-embed.html site="Vimeo" id="22439234" alt="The Mountain" %}

```liquid
{% raw %}{% include video-embed.html site="Vimeo" id="22439234" alt="The Mountain" %}{% endraw %}
```

## YouTube

IDs are just the `v` value in the URL, e.g. [youtube.com/watch?v=T1itpPvFWHI][youtube]

[youtube]: https://www.youtube.com/watch?v=T1itpPvFWHI

{% include video-embed.html site="YouTube" id="T1itpPvFWHI" alt="Introduction | Jekyll - Static Site Generator | Tutorial 1" %}

```liquid
{% raw %}{% include video-embed.html site="YouTube" id="T1itpPvFWHI" alt="Introduction | Jekyll - Static Site Generator | Tutorial 1" %}{% endraw %}
```
