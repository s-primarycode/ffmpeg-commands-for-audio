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
