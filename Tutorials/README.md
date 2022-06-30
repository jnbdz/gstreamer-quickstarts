# Tutorials | GStreamer | Quickstarts
You can download this video for the tutorial: https://durian.blender.org/download/

## Hello World!
For the Hello World! we will play the video: Sintel.

In this directory you will find `basic-tutorial-1`.

To compile: 
```bash
gcc basic-tutorial-1.c -o basic-tutorial-1 `pkg-config --cflags --libs gstreamer-1.0`
```
Execute: 
```bash
./basic-tutorial-1
```
You should see a window popup with a video playing (it uses buffering so with slow internet you will see it pause).

The video that plays is from: https://www.freedesktop.org/software/gstreamer-sdk/data/media/sintel_trailer-480p.webm

**Breakdown:** 
```c
/* Initialize GStreamer */
gst_init (&argc, &argv);
```
*Is required*
- Initializes all internal structures
- Checks what plug-ins are available
- Executes any command-line option intended for GStreamer

The command-line parameters are pass to `gst_init` so that you can benefit from GStreamer standard command-line options.

```c
pipeline =
      gst_parse_launch
      ("playbin uri=https://www.freedesktop.org/software/gstreamer-sdk/data/media/sintel_trailer-480p.webm",
      NULL);
```
- [`gst_parse_launch`](https://gstreamer.freedesktop.org/documentation/gstreamer/gstparse.html#gst_parse_launch) - Used for simple piplines (shortcut). It converts textual representation of a pipeline into an actual pipeline 
- [playbin](https://gstreamer.freedesktop.org/documentation/playback/playbin.html#playbin) - 

## Resources
- [Tutorials | gstreamer.freedesktop.org](https://gstreamer.freedesktop.org/documentation/tutorials/index.html?gi-language=c) - This version is for *C* but you can follow the tutorial with *Python* or even *JavaScript*.
### Codecs
- [Video Encoding Basics: What is a Video Codec? - Haivision](https://www.haivision.com/blog/all/video-encoding-basics-what-is-a-video-codec/)
### Videos
- [Using GStreamer | YouTube](https://www.youtube.com/watch?v=ZphadMGufY8)
- [Introduction to Gstreamer (Gst-launch) for embedded devices raspberry pi jetson nano | YouTube](https://www.youtube.com/watch?v=rPcQiDHyGnI)
- [Jetson Xavier NX Lesson 4: Understanding Gstreamer for Absolute Beginners | YouTube](https://www.youtube.com/watch?v=_yU1kfcC6rY)
#### Codecs
- [How Codecs Work - Tutorial | Vimeo](https://vimeo.com/104554788)
- [Video Codecs & Compression Guide (Feat. Atomos Ninja V) | YouTube](https://www.youtube.com/watch?v=wX9KGRHaMEY)
- [How to Understand Codecs | YouTube](https://www.youtube.com/watch?v=sisvOeZItb0)
