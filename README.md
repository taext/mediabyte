


# Mediabyte 
### v0.8.6.6

<br>

The **mediabyte** format is an open-source poly-platform playlist format and succinct online media referencing syntax.

<br>

### Scope
The Online Media Metadata (OMM) mediabyte format is
- an open-source online media playlist format
- an online media referencing format 
  - a succinct alternative to the URL format
  - with optional explicit metadata (title, tags, time codes)
- a simple Mixtape HTML player
- a Python API for hacking with the format
- friendly with Jupyter Notebook

<br>

### Value Proposition

- tag the content of specific YouTube videos
  - e.g. to help discoverability of favourite content
- remix YouTube videos with 1-second precision 
  - e.g. to create a topical mix of clips from a video series
- play a YouTube search directly
- reference, tag and access any online content
  - native Bitly hash support (incl. custom hashes)
- index and remix podcast episodes
  - native MP3 support

<br>




<br>


### .omm Mixtape file

![OMM syntax highlight example](https://v1d.dk/omm/omm_syntax_highlight.jpg)

<br>


### The mediabyte tag syntax

1. tags are separated by dots
2. capitalized tags are titles
3. YouTube time code tags are such
4. remaining tags are ordinary tags
5. **y.youtubehash** or **b.bitlyhash** is mandatory
6. all other tags are optional

<br>


### The yota objects: Yota, Cue, Sample, Mixtape

1. a yota with no start code is a **Yota** object (the original YouTube video)
2. a yota with a start time code is a **Cue** object (the YouTube video with a start time)
3. a yota with start and end time codes is a **Sample** object (the YouTube video clip)
4. a **Mixtape** is a collection of **Yota**, **Cue**, **Sample**, and **bit** objects



Check out the mediabyte [documentation](https://github.com/taext/mediabyte/blob/master/user_guide/README.md) for details and examples.

<br>

### The bit objects: Link and Mp3 (beta)

1. a **bit.Link** is a bitly link: `b.bitlyhash` (general link support)
2. a **bit** can have title and tags (just like the yota objects)
3. a **bit** can be a yota tag `y.youtubehash.b.bitlyhash` or stand alone
2. a **bit.Mp3** - a **bit.Link** with the tag `mp3` - is a bitly MP3 link (MP3 support)
3. a **bit.Mp3** has 0-2 time codes, yota-style handling and VLC playback



<br>


### Project Status

The mediabyte back-end is feature-complete.

The mediabyte syntax is feature-complete.

General interface `omm()` to parse any mediabyte string, Mixtape file or Mixtape link.

Syntax highlighting and `.omm` file association using the contained Atom [package](https://github.com/taext/mediabyte/tree/master/atomSyntaxHighlighting). (beta)

Search YouTube directly and get results in **Mixtape** with `youtube('copenhagen 10')`.

Search auto-generated subtitles with `Yota.srt_search` and `Mixtape.srt_search`. (linux only) (beta)

**Mixtape** files [supports](https://github.com/taext/mediabyte/blob/master/user_guide/Demo:%20Mixtape%20Arbitrary%20White-Space.ipynb) arbitrary white-space. (freestyle formatting)

Bitly links. (general link support)

Custom Bitly link support, e.g. `b.sn-704.Security Now`. (a title tag is needed, to be fixed)

MP3 support.

Pip installation `pip install mediabyte`.

Windows 10 support. (beta)

`mediabyte.hash` referencing: `o.diu5ir4jkk3` (full hash) or `omm('o.diu')` (uniquely match).

[Write](https://github.com/taext/mediabyte/blob/master/user_guide/Demo:%20bit.Mp3%20Mixtape%20Cutting.ipynb)  bit.MP3 **Mixtape** chapters to MP3s or splice chapters to single **Mixtape** MP3. (MP3 remixing) (alpha)

[Load](https://github.com/taext/mediabyte/blob/master/user_guide/Demo:%20Online%20.omm%20support.ipynb) online .omm **Mixtape** files.

Search history with `search('podcast')`. (tag, title or mediabyte hash search)

Convert saved YouTube .htm file to **Mixtape**.

Convert YouTube Takeout watch history file to **Mixtape**.

Online mediabyte/Mixtape URL [player](http://www.mediabyte.xyz/).

Online YouTube search to [player](http://www.mediabyte.xyz/search).


<br>

Currently the output options are: 

- basic continuous HTML/JavaScript [player](https://v1d.dk/yno/mix22.htm), HTML [Wall-of-TV](https://v1d.dk/yno/mix22_iframe.htm), HTML [links](https://v1d.dk/yno/mix22_html.htm), VLC playback* and open in tabs for **Mixtape**

- VLC playback, HTML Iframe and open in tab for **Sample**, **Cue**
  and **Yota**

- VLC playback and open in tab for **bit.Link**

- VLC playback for **bit.Mp3**

- **Mixtape** MP3 or **Sample** MP3s for **bit.Mp3** **Mixtape**

<br>

\* currently Yota-only Mixtapes


<br>


                                        Updated May 2nd 2019
