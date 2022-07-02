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

## Module inspection
### Audio Test
Test audio: 
```bash
gst-launch-1.0 audiotestsrc ! alsasink
```
To inspect a module: 
```bash
gst-inspect-1.0 audiotestsrc
```
**Output:**

Name, source, etc: 
```
Factory Details:
  Rank                     none (0)
  Long-name                Audio test source
  Klass                    Source/Audio
  Description              Creates audio test signals of given frequency and volume
  Author                   Stefan Kost <ensonic@users.sf.net>

Plugin Details:
  Name                     audiotestsrc
  Description              Creates audio test signals of given frequency and volume
  Filename                 /usr/lib/x86_64-linux-gnu/gstreamer-1.0/libgstaudiotestsrc.so
  Version                  1.20.3
  License                  LGPL
  Source module            gst-plugins-base
  Source release date      2022-06-15
  Binary package           GStreamer Base Plugins (Debian)
  Origin URL               http://packages.qa.debian.org/gst-plugins-base1.0

GObject
 +----GInitiallyUnowned
       +----GstObject
             +----GstElement
                   +----GstBaseSrc
                         +----GstAudioTestSrc
```

- `src` means source
- Source also known as *output* that the *sink* takes in

In this case this module is a source: 
```
Pad Templates:
  SRC template: 'src'
    Availability: Always
```

These are the formats that it supports (what it can do): 
```
    Capabilities:
      audio/x-raw
                 format: { (string)S16LE, (string)S16BE, (string)U16LE, (string)U16BE, (string)S24_32LE, (string)S24_32BE, (string)U24_32LE, (string)U24_32BE, (string)S32LE, (string)S32BE, (string)U32LE, (string)U32BE, (string)S24LE, (string)S24BE, (string)U24LE, (string)U24BE, (string)S20LE, (string)S20BE, (string)U20LE, (string)U20BE, (string)S18LE, (string)S18BE, (string)U18LE, (string)U18BE, (string)F32LE, (string)F32BE, (string)F64LE, (string)F64BE, (string)S8, (string)U8 }
                 layout: { (string)interleaved, (string)non-interleaved }
                   rate: [ 1, 2147483647 ]
               channels: [ 1, 2147483647 ]

Element has no clocking capabilities.
Element has no URI handling capabilities.

Pads:
  SRC: 'src'
    Pad Template: 'src'
```

These are the properties that you can set: 
```

Element Properties:
  apply-tick-ramp     : Apply ramp to tick samples
                        flags: readable, writable
                        Boolean. Default: false
  blocksize           : Size in bytes to read per buffer (-1 = default)
                        flags: readable, writable
                        Unsigned Integer. Range: 0 - 4294967295 Default: 4294967295 
  can-activate-pull   : Can activate in pull mode
                        flags: readable, writable
                        Boolean. Default: false
  can-activate-push   : Can activate in push mode
                        flags: readable, writable
                        Boolean. Default: true
  do-timestamp        : Apply current stream time to buffers
                        flags: readable, writable
                        Boolean. Default: false
  freq                : Frequency of test signal. The sample rate needs to be at least 2 times higher.
                        flags: readable, writable, controllable
                        Double. Range:               0 -    1.073742e+09 Default:             440 
  is-live             : Whether to act as a live source
                        flags: readable, writable
                        Boolean. Default: false
  marker-tick-period  : Make every Nth tick a marker tick (= a tick with different volume). Only used if wave = ticks. 0 = no marker ticks.
                        flags: readable, writable
                        Unsigned Integer. Range: 0 - 4294967295 Default: 0 
  marker-tick-volume  : Volume of marker ticks. Only used if wave = ticks andmarker-tick-period is set to a nonzero value.
                        flags: readable, writable
                        Double. Range:               0 -               1 Default:               1 
  name                : The name of the object
                        flags: readable, writable, 0x2000
                        String. Default: "audiotestsrc0"
  num-buffers         : Number of buffers to output before sending EOS (-1 = unlimited)
                        flags: readable, writable
                        Integer. Range: -1 - 2147483647 Default: -1 
  parent              : The parent of the object
                        flags: readable, writable, 0x2000
                        Object of type "GstObject"
  samplesperbuffer    : Number of samples in each outgoing buffer
                        flags: readable, writable
                        Integer. Range: 1 - 2147483647 Default: 1024 
  sine-periods-per-tick: Number of sine wave periods in one tick. Only used if wave = ticks.
                        flags: readable, writable
                        Unsigned Integer. Range: 1 - 4294967295 Default: 10 
  tick-interval       : Distance between start of current and start of next tick, in nanoseconds.
                        flags: readable, writable
                        Unsigned Integer64. Range: 1 - 18446744073709551615 Default: 1000000000 
  timestamp-offset    : An offset added to timestamps set on buffers (in ns)
                        flags: readable, writable
                        Integer64. Range: -9223372036854775808 - 9223372036854775807 Default: 0 
  typefind            : Run typefind before negotiating (deprecated, non-functional)
                        flags: readable, writable, deprecated
                        Boolean. Default: false
  volume              : Volume of test signal
                        flags: readable, writable, controllable
                        Double. Range:               0 -               1 Default:             0.8 
  wave                : Oscillator waveform
                        flags: readable, writable, controllable
                        Enum "GstAudioTestSrcWave" Default: 0, "sine"
                           (0): sine             - Sine
                           (1): square           - Square
                           (2): saw              - Saw
                           (3): triangle         - Triangle
                           (4): silence          - Silence
                           (5): white-noise      - White uniform noise
                           (6): pink-noise       - Pink noise
                           (7): sine-table       - Sine table
                           (8): ticks            - Periodic Ticks
                           (9): gaussian-noise   - White Gaussian noise
                           (10): red-noise        - Red (brownian) noise
                           (11): blue-noise       - Blue noise
                           (12): violet-noise     - Violet noise
```
*Source: [audiotestsrc](./audiotestsrc.txt)*

To use the param: 
```bash
gst-launch-1.0 audiotestsrc wave=1 volume=1 ! alsasink
```
> **WARNING!** Very loud sound!

> **NOTE:** Sometimes the `!` setting the caps or filter not just passing to the other module.

> **IMPORTANT!** Inspect also the sync (module) to make sure it supports the format that is ouputed.

- *caps* setting caps you will need `,` between settings

Example with *caps* (where the audio format is changed): 
```bash
gst-launch-1.0 audiotestsrc wave=1 freq=300 volume=0.1 ! audio/x-raw,format=U8 ! alsasink
```

Example with a converter: 
```bash
gst-launch-1.0 audiotestsrc wave=1 freq=300 volume=0.1 ! audio/x-raw,format=U18LE ! audioconvert ! alsasink
```
> `audioconvert` will identify what the *sink* needs as input format and will convert the audio from the output into that format automatically.

You can always do it manually by using `gst-inspect-1.0` to find out the supported formats.

### Video Test
```bash
gst-launch-1.0 videotestsrc ! ximagesink
```
You will see an basic video in a small popup window.



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
