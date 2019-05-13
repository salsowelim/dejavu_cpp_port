
Dejavu c++ port (audio fingerprinting)
==========

This is a c++ implementation of the fingerprinting algorithm suggested in the [dejavu audio fingerprinting project] (https://github.com/worldveil/dejavu) (specifically: the fingerprint.py file). [link on how dejavu works](http://willdrevo.com/fingerprinting-and-audio-recognition-with-python/)

## Prerequisites:
- opencv (= 3.4.5)
- boost library (= 1.60)
- c++14
- for demo only: ffmpeg

The "fingerprint" function will accept array of floats as an input (raw audio pcm data). It will returns a list of hashes with offsets (as a json string).

## Why the c++ port?
1. You can run c++ code on iOS (tested it myself, works Flawlessly), or android (possible using NDK I guess?).
2. In theory: performance boost. In practise: didn't see much difference.

## Demo
The main function will load a test mp3 file, uncompressed it using ffmpeg (as a mono channel, 22050 sample rate), feed it to fingerprint function, then prints the list of hashes-offsets.  

## Final notes
- I don't have much experience working with c++. I wrote this code initially for prototype purposes. while I have tested the correctness of the algorithm output, I didn't optimise the code to c++ best standards. If you want to improve the code in this manner I will gladly accept pull requests.
- Performance (speed wise) is really slow when the audio input is large. However on small audio files (<10 seconds) it is similar or better than python implementation. For now, I'm not interested to look after this issue. If you have a fix, PR.
