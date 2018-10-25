# MPD_dashdata
From big buck bunny  10 min (9.56min)video  https://goo.gl/m4RgSH we create mpd file; 

Segment duraion- 4 min ;

Total segment- 149 for each representation;

here we use 10 bitrate representation;

At first encode video with X264 tool and create segment with MP4Box tool

$ x264 --output intermediate_235k.264 --fps 24 --preset slow --bitrate 235 --vbv-maxrate 470 --vbv-bufsize 940 --min-keyint 96 --keyint 96 --scenecut 0 --no-scenecut --pass 1 --video-filter "resize:width=320,height=240"  sample.mp4

$ MP4Box -add intermediate_235k.264 -fps 24 output_235k.mp4

$ MP4Box -dash 4000 -profile dashavc264:live -frag 4000 -rap  -segment-name 320x240_235kbps_24fps_10min_segment output_235k.mp4
https://bitmovin.com/mp4box-dash-content-generation-x264/

No.of Bitrate Representation--Resolution----Bitrate(Encoding)----Rate Quality Level

1. -------------------------------320x240-------235kbps-----very low quality

2. -------------------------------384x288-------375 kbp-----slow quality

3. -------------------------------512x384-------560 kbps----VHS-ish quality

4. -------------------------------512x384-------750 kbps----better VHS-ish qualit

5. -------------------------------640x480-------1050 kbps---analog TV quality

6. -------------------------------720x480-------1750 kbps---DVD-ish quality

7. -------------------------------1280x720------2350 kbps---720p low quality

8. -------------------------------1280x720------3000 kbps---720p high quality

9. -------------------------------1920x1080-----3850 kbps---1080p low quality

10. ------------------------------1920x1080-----4300 kbps---1080p medium quality
