# How to ... Streaming !

## Stream with ffmpeg [source](https://superuser.com/questions/1480038/ffmpeg-stream-test-pattern-to-vlc-via-tcp)

start stream:
```
ffmpeg -f lavfi -i testsrc=size=800x600:rate=24 -c:v libx264 -tune zerolatency -pix_fmt yuv420p -profile:v baseline -b:v 300K -minrate 100K -maxrate 1M -bufsize 2M -g 24 -f mpegts tcp://127.0.0.1:1234\?listen
```

open it in vlc with:
```
tcp://@:1234
```
