
##dejavu c++ port (audio fingerprinting library)

This is a c++ implementation of the fingerprinting algorithm suggested in the dejavu audio fingerprinting library (specifically: the fingerprint.py file). (link on how dejavu works).

prerequisites:
- opencv (= 3.4.5)
- boost library (= 1.60)
- c++14
- for demo only : ffmpeg

The "fingerprint" function will accept array of  floats as an input (raw audio pcm data). It will returns a list of hashes with offset (as a json string).

Demo: the main function will load a test mp3 file, uncompressed it using ffmpeg ( as a mono channel, 22050 sample rate), then feed to fingerprint function, then prints the list of hashes-offsets.  

Why the c++ port?
1. You can run c++ code on iOS ( tested it myself, works Flawlessly), or android ( possible using NDK I guess?).
2. In theory: performance boost. In practise: didn't see much difference.

Final notes:
- I don't have much experience working with c++. I wrote this code initially for prototype purposes. while I have tested the correctness of the algorithm output, I didn't optimise the code to c++ best standards.  If you want to improve the code in this manner I will gladly accept pull requests.
- Performance (speed wise) is really slow when the audio input is large. however on small audio files (<10 seconds) it is similar or better than python implementation. for now, I'm not interested to look for this issue. If you have a fix, PR.
