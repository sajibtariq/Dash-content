# MPD_dashdata

## How to create dash content

- Step 1: [Encode video with X264 tool and create segment with MP4Box tool](https://bitmovin.com/mp4box-dash-content-generation-x264/)

- Step 2: $ x264 --output intermediate_235k.264 --fps 24 --preset slow --bitrate 235 --vbv-maxrate 470 --vbv-bufsize 940 --min-keyint 96 --keyint 96 --scenecut 0 --no-scenecut --pass 1 --video-filter "resize:width=320,height=240"  sample.mp4
- Step 3: $ MP4Box -add intermediate_235k.264 -fps 24 output_235k.mp4
- Step 4: $ MP4Box -dash 4000 -profile dashavc264:live -frag 4000 -rap  -segment-name 320x240_235kbps_24fps_10min_segment output_235k.mp4

## Content information

- Animation: [Big Buck Bunny](https://goo.gl/m4RgSH )
- Duration: 9.56 min 
- Segment duraion: 4 min 
- Total segment: 149 for each representation;

| No.of Bitrate Representation | Resolution | Bitrate(Encoding) | Rate Quality Level| 
| :---:   | :-: | :-: | :---:   | 
| 1 | 320x240 |235kbps |very low quality | 
| 2 | 384x288 |375kbps |slow quality | 
| 3 | 512x384 |560kbps |VHS-ish quality|
| 4 | 512x384 |750kbps |better VHS-ish qualit |
| 5 | 640x480 |1050 kbps |analog TV quality |
| 6 | 720x480 |1750kbps |DVD-ish quality |
| 7 | 1280x720 |2350kbps |720p low quality|
| 8 | 1280x720 |3000kbps |720p high quality |
| 9 | 1920x1080|3850kbps |1080p low quality |
| 10 | 1920x1080 |4300kbps |1080p medium quality|


