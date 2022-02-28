# Screen sharing and WebRTC on the Oculus Quest

## Good news

It works well (tested in the built-in browser), at least for audio.

## Bad news

There is no video going out of the oculus, nor the pass through cam nor desktop sharing.

It seems that in WebRTC extra care needs to be taken to make assymetric connections (eg. Desktop share from PC, Voice-only from Oculus) work. 

In https://github.com/anoek/webrtc-group-chat-example I could get no video received on the audio side.

However, it is possible to get it working as it does indeed work in https://livelab.app