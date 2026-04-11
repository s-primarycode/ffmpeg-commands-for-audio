# ffmpeg-commands-for-audio
---
**WEBP to JPG High Definition**
	
	ffmpeg -i input.webp -q:v 1 output.jpg
  
**Slightly compress m4a**

	ffmpeg -i input.m4a -map 0 -map_metadata 0 -c:a aac -b:a 96k -c:v copy output.m4a

**Slightly compress m4a folders**

	for %f in (*.m4a) do ffmpeg -i "%f" -map 0 -map_metadata 0 -c:a aac -b:a 96k -c:v copy "%~nf_compressed.m4a"

**FLAC folder to M4A**

	for %f in (*.flac) do ffmpeg -i "%f" -c:a alac "%~nf.m4a"


For Linux

	ffmpeg -i song.flac -i cover.jpg \
	-map 0:a -map 1:v \
	-c:a aac -b:a 192k \
	-c:v mjpeg \
	-disposition:v:0 attached_pic \
	-metadata title="Blinding Lights" \
	-metadata artist="The Weeknd" \
	-metadata album="After Hours" \
	-metadata genre="Pop" \
	-metadata date="2020" \
	song.m4a
