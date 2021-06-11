WebRTC Audio Latency Test 
==============
## Usage
- Please make sure to use Chrome/a Chromium-based browser (tested with version 91)

The signaling server uses Node.js and `ws` and can be started as such:

```
$ npm install
$ npm start
```

With the server running, open a recent version of Firefox, Chrome, or Safari and visit `https://localhost:8443`.

* Note the HTTPS! There is no redirect from HTTP to HTTPS.
* Some browsers or OSs may not allow the webcam to be used by multiple pages at once. You may need to use two different browsers or machines.


## Test locally on the same machine
- Open two tabs, visit `https://localhost:8443` and press "start audio" on either one of them
- Mute all audio elements in one of the two tabs
- Capture computer playback
    - helpful guide: https://manual.audacityteam.org/man/tutorial_recording_audio_playing_on_the_computer.html
- Make some noise e.g. snapping with your fingers
- Look at the audio file using a sound editor like Audacity and calculate the delta between the peaks
    - Audacity shows the length of a marked section in the lower panel if set to "Start and Length of Section"

## Test using multiple machines (loopback)
- One peer visits `https://localhost:8443` (or the respective ip instead of localhost)
- The other peer visits `https://localhost:8443/loopback`. This clients only sends back the audio it receives.
- Make a measurement as previously described using the non-loopback client

### Ideas for improvement
- Experiment with tweaks from https://webrtc.github.io/samples/src/content/peerconnection/audio/ and constraints 
- Automate measurement (i.e virtual speaker, microphone; selenium/puppeteer), automate calculation 
- Make loopback work in Firefox
- Make it portable (containerization/virtualization)

</br>

---
</br>

## Forked from WebRTC-Example

#### shane tully (shanetully.com)

An 'as simple as it gets' WebRTC example.

See [https://shanetully.com/2014/09/a-dead-simple-webrtc-example/](https://shanetully.com/2014/09/a-dead-simple-webrtc-example/) for a detailed walkthrough of the code.

Note: This repo is kept updated. The general ideas are there, but the above blog post may be somewhat out of date with the code in this repo.


## License

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
