# ffmpeg scripts


# split mp3 into 1 minute long parts

```bash
ffmpeg -i input.mp3 -f segment -segment_time 60 -c copy -reset_timestamps 1 output_%03d.mp3
```

* -i input.mp3. Specifies the input audio file.
* -f segment. use the FFmpeg segment muxer to split the file into multiple outputs.
* -segment_time 60. Sets the duration of each split part to 60 seconds.
* -c copy. Copies the existing audio stream directly without re-encoding
* -reset_timestamps 1. Resets the timestamp of each resulting clip back to 00:00 so every file plays properly from the start.
* output_%03d.mp3. Names the generated files sequentially with three-digit padding 
