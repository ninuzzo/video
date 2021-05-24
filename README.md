# video
Easy to use script for most common ffpmeg video editing tasks

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
    cut	  in start out [end|+duration] -precise
    info      in
    transpose in cclock_flip|clock|cclock|clock_flip out
    segment	  in [outbasename]
    title     image duration out [size] [framerate]
    video	  extract in out
              speed in fraction out [duration]

# Example

Replace audio, then precisely cut a video from 00:00:05 to 00:00:40:

    $ video audio replace video.mp4 new_audio.mp3 temp.mp4, cut temp.mp4 00:00:05 new_video.mp4 00:00:40 -precise
