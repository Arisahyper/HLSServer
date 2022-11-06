```
ffmpeg -i BachGavotteShort.mp3 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list outputlist.m3u8 -segment_format mpegts output%03d.ts
```

## ダメな例
```
ffmpeg -i starry-jet.mp4 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list outputlist.m3u8 -segment_format mpegts output%03d.ts
```

```
ffmpeg -i starry-jet.mp4 -c:v copy -c:a copy -f hls -hls_time 9 -hls_playlist_type vod -hls_segment_filename "output%3d.ts" outputlist.m3u8
```

```
go run .
```

```
http://localhost:8080/videos/starry/outputlist.m3u8
http://localhost:8080/songs/outputlist.m3u8
```
