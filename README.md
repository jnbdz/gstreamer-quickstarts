<img src="assets/Gstreamer-logo.svg" alt="GStreamer logo" style="width: 215px;" align="right">

# gstreamer-quickstarts
GStreamer quickstarts

## Media Streaming Standards
- [MPEG transport stream | Wikipedia](https://en.wikipedia.org/wiki/MPEG_transport_stream) - *MPEG transport stream (MPEG-TS, MTS) or simply transport stream (TS) is a standard digital container format for transmission and storage of audio, video, and Program and System Information Protocol (PSIP) data.[5] It is used in broadcast systems such as DVB, ATSC and IPTV.* (file ext: `.ts, .tsv, .tsa, .m2t`, mime type: `video/MP2T`)
- [Dynamic Adaptive Streaming over HTTP | Wikipedia](https://en.wikipedia.org/wiki/Dynamic_Adaptive_Streaming_over_HTTP) - *Dynamic Adaptive Streaming over HTTP (DASH), also known as MPEG-DASH, is an adaptive bitrate streaming technique that enables high quality streaming of media content over the Internet delivered from conventional HTTP web servers.* (file extension: `.ts, .tsv, .tsa, .m2t`, mime type: `video/MP2T`) (example of content generator: [MP4Box | Wikipedia](https://en.wikipedia.org/wiki/MP4Box) used by [Télécom Paris | Wikipedia](https://en.wikipedia.org/wiki/T%C3%A9l%C3%A9com_Paris))
- [HTTP Live Streaming | Wikipedia](https://en.wikipedia.org/wiki/HTTP_Live_Streaming) - *HTTP Live Streaming (also known as HLS) is an HTTP-based adaptive bitrate streaming communications protocol developed by Apple Inc. and released in 2009.* (file ext: `.m3u8`, mime type: `application/vnd.apple.mpegurl` or `audio/mpegurl`)

## Resources
- [GDtreamer official website](https://gstreamer.freedesktop.org/)
- [GStreamer GitHub mirrors | GitHub](https://github.com/GStreamer)
- [GStreamer | Documentation](https://gstreamer.freedesktop.org/documentation/?gi-language=c)
- [Fundamentals of AV over IP | Matrox Video](https://www.matrox.com/en/video/media/guides-articles/fundamentals-of-av-over-ip)
- [OpenHMD | Free and Open Source API and drivers for immersive technology](https://github.com/OpenHMD)
- [GStreamer Network Video Stream and Save to File | jetsonhacks.com](https://jetsonhacks.com/2014/10/28/gstreamer-network-video-stream-save-file/)
### CheatSheet
- [GStreamer command-line cheat sheet | GitHub](https://github.com/jnbdz/gstreamer-cheat-sheet)
- [GStreamer Pipelines | GitHub](https://github.com/jnbdz/gstreamerCheatsheet)
### Help
- [GStreamer Appchat - gstreamer freenode - GStreamer, Multimedia | en.irc2go.com](https://en.irc2go.com/webchat/?net=freenode&room=gstreamer)
    - <a href="irc://chat.freenode.net:6667/">irc://chat.freenode.net:6667/</a>
    - <a href="ircs://chat.freenode.net:6697/">ircs://chat.freenode.net:6697/</a>
### Alternatives
- [OpenMAX Overview - The Khronos Group Inc](https://www.khronos.org/openmax/)
### Companies that use GStreamer
- [Thermal Imaging, Night Vision and Infrared Camera Systems | Teledyne FLIR](https://www.flir.ca/)
### StackExchange Questions
- [gst-launch-1.0 freezes when I use autovideoconvert and I don't see the test video | superuser.com](https://superuser.com/questions/1729565/gst-launch-1-0-freezes-when-i-use-autovideoconvert-and-i-dont-see-the-test-vide)
### Video
- [Gstreamer RTSP Server Client to get audio working on Windows 10 Hyper-V virtual machine Ubuntu 20.04 | YouTube](https://www.youtube.com/watch?v=VYbOBTeLIq0)
### Tools
- [HEVCESBrowser | GitHub](https://github.com/jnbdz/hevcesbrowser) - HEVCESBrowser is a tool for analyzing HEVC(h265) bitstreams.
- [QHexView | GitHub](https://github.com/jnbdz/QHexView) - This is Qt widget for display binary data in traditional hex-editor style. This widget doesn`t have any editing capabilities. Only viewing and copying.
- [gdpviewer | GitHub](https://github.com/virinext/gdpviewer) - Gdpviewer is a gui tool for diaplaying gstreamer gdp data. This is for debugging gstreamer`s plugins and pipelines.
- [pipeviz | GitHub](https://github.com/jnbdz/pipeviz) - Pipeviz is a graphedit for gstreamer-1.0. This is a gui tool for constructing and testing gstreamer pipelines.
- [AC3ESBrowser | GitHub](https://github.com/jnbdz/ac3esbrowser) - AC3ESBrowser is a tool for analyzing Dolby Digital and Dolby Digital Plus bitstreams.
### Other
- [GPAC | Multimedia Open Source Project](http://gpac.io/) ([GPAC | GitHub](https://github.com/gpac/gpac)) - *Modular Multimedia framework for packaging, streaming and playing your favorite content.*
    - [MP4Box | GitHub](https://github.com/gpac/gpac/wiki/MP4Box) - The multimedia packager available in GPAC is called MP4Box. It is mostly designed for processing ISOBMF files (e.g. MP4, 3GP), but can also be used to import/export media from container files like AVI, MPG, MKV, MPEG-2 TS.
- `mediainfo` - command line utility to display information about audio/video files
- [TSDuck, The MPEG Transport Stream Toolkit](https://tsduck.io/) - *TSDuck is an extensible toolkit for MPEG transport streams. It is used in digital television systems for test, monitoring, integration, debug, lab, demo.*
- [ExoPlayer](https://exoplayer.dev/) - *ExoPlayer is an application level media player for Android. It provides an alternative to Android’s MediaPlayer API for playing audio and video both locally and over the Internet. ExoPlayer supports features not currently supported by Android’s MediaPlayer API, including DASH and SmoothStreaming adaptive playbacks. Unlike the MediaPlayer API, ExoPlayer is easy to customize and extend, and can be updated through Play Store application updates.*
