bmd-tools
=========

Tools to connect with and manage Blackmagic Design video
equipment with built-in H.264 encoder.

Currently tested device:

 * ATEM TV studio
 * H.264 Pro Recorder

Use *bmd-extractfw* to extract the firmware out from
BMDStreamingServer.exe (part of the Windows drivers).

*bmd-streamer* can be used to upload the extracted firmwares,
and to stream out (currently to stdout) the MPEG TS stream
from the device. For example, to sent stream as clean
MPEG-TS via RTP do "bmd-streamer | multicat /dev/stdin IP:PORT -u".

On remote side for example you can use Raspberry Pi to do clean hardware decoding
(including interlacing support and clock recovery) by using
"omxplayer -s -w -y -r -b -o hdmi --nativedeinterlace --no-osd --no-keys --live rtp://IP:PORT"

Dependencies:
 * libusb (1.0.16 or newer) or libusbx


Install build requirements (Raspian/Ubuntu/Debian):
sudo apt-get install git build-essential libusb-1.0-0-dev
