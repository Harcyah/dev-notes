# How to ... Streaming !

## TCP stream with ffmpeg [source](https://superuser.com/questions/1480038/ffmpeg-stream-test-pattern-to-vlc-via-tcp)

start stream:
```
ffmpeg \
    -f lavfi \
    -i testsrc=size=800x600:rate=24 \
    -c:v libx264 \
    -tune zerolatency \
    -pix_fmt yuv420p \
    -profile:v baseline \
    -b:v 300K \
    -minrate 100K \
    -maxrate 1M \
    -bufsize 2M \
    -g 24 \
    -f mpegts tcp://127.0.0.1:1234\?listen
```

open it in vlc with:
```
tcp://@:1234
```

## RTP stream with ffmpeg [source](https://superuser.com/questions/1480038/ffmpeg-stream-test-pattern-to-vlc-via-tcp)

start stream:
```
ffmpeg \
    -f lavfi \
    -i testsrc=size=800x600:rate=24 \
    -c:v libx264 \
    -tune zerolatency \
    -pix_fmt yuv420p \
    -profile:v baseline \
    -b:v 300K \
    -minrate 100K \
    -maxrate 1M \
    -bufsize 2M \
    -g 24 \
    -f rtp rtp://127.0.0.1:1234
```

ffmpeg will output a sdp file, similar to:

```
v=0
o=- 0 0 IN IP4 127.0.0.1
s=No Name
c=IN IP4 127.0.0.1
t=0 0
a=tool:libavformat 58.20.100
m=video 1234 RTP/AVP 96
b=AS:300
a=rtpmap:96 H264/90000
a=fmtp:96 packetization-mode=1
```

copy/paste this sdp in some random file, and open this file with vlc.
