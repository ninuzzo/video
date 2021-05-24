# video
Easy to use script for most common ffmpeg video editing tasks.

# Command line usage

    $ video help
    Usage: video subcommand... [arg]... [, subcommand... [arg]...]
    TIME format is HH:MM:SS.xxx or s.msec
    Subcommands (can be shortened):
    
    yes       (no overwrite confirmation)
    no        (overwrite confirmation)
    audio     extract in out
              replace in audio out -shortest
    concat    in... out
    cut       in start out [end|+duration] -precise
    info      in
    transpose in cclock_flip|clock|cclock|clock_flip out
    segment   in [outbasename]
    title     image duration out [size] [framerate]
    video     extract in out
              speed in fraction out [duration]

# Examples

- Replace audio, then precisely cut a video from 00:00:05 to 00:00:40:

    $ video audio replace video.mp4 new_audio.mp3 temp.mp4, \
        cut temp.mp4 00:00:05 new_video.mp4 00:00:40 -precise

- Generate a 5 seconds title from statis image title.png at full HD resolution, with 30 frames per second. Do not prompt if overwriting the title.mp4 output file:

    $ video yes title title.png 5 title.mp4 1920:1080 30

- Extract audio and video from clip.mp4 into audio-only.mp3 and video-only.mp4 respectively:

    $ video yes audio extract clip.mp4 audio-only.mp3, video extract clip.mp4 video-only.mp4

