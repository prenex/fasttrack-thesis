Fasttrack marker tracking
=========================

### Introduction, short description

This repository contains my MSc thesis text in Hungarian language about . This basically serves as a documentation alongside the "fasttrack" project too - which project is also here on git.

My goal with the "fasttrack" project is to try creating a marker tracking algorithm that is implemented with no-to-minimal dependencies and utilize only one scan over the whole image as a so-called "online algorithm". First color-based markers were considered, but later this has been changed to a more generic approach using three layers of the process of 2D marker recocnition:

1.) The low-layer is a very fast path for each pixel of the image. It basically processes them to generate "areas" fur further per-scanline processing. This has a "next(MAG)" operation.
2.) The mid-layer is like a loose-rule parser engine over the low-layer and finds "1D marker center positions" per scanline. This operation was be tested per-scanline and it runs online with the low-layer. This both has a "next(MAG)" and an "endLine()" operation and returns per-line results for the caller.
3.) The high-layer comes into the situation lastly and this keeps data between consequtive scanlines so that it can look for "2D marker centers". This is implemented in MCParser in a generic way that enables us to exchange the low- and mid-layers and the type used for "pixel magnitude" without needing any changes in itself. This layer works online with the above two algorithms and it tries to ensure being cache-friendly with least amount of rare-case holes in the instruction cache.

Also a main design point was to have an algorithm that scales very well when growing the numbers of 2D markers found on the camera and providing a stable high frame rate. Most marker-tracking algorithms consider the marker to be a 3D tracking primitive in itself and scales badly when more and more visible markers are being added. This algorithm however handles high number of 2D markers nearly as fast like one or two and might handle hundreds of them - given they can coexist in the scene.

Circular shapes are used because their projected images always form cones and ellipses regardless of how the scanlines are positioned through the real world object.

The algorithm itself can be made parallel easily, but I am designing the algorithms for low-end or embedded usage scenarios and implement this mostly at my home machine only having one core. It uses instruction level parallelism and contains hand-optimized C++ code with through profiling for cache efficiency both on old and new machine architectures.

**Possible usages:**

* "Traditional AR": Construct a 3D marker out of 4 corners of a paper printed with 2D fasttrack markers: can use p4p and similar algorithms.
* "Positioning/Mapping": Construct many 3D markers out of only triangles of 2D fasttrek markers and g-sensor data to help finding the solution. Markers do not need g-sensor, but need to be oriented properly!
* "Light-gun": Construct a "mouse emulator" for linux by putting 2D fasttrek markers near the 4 corners of your monitor or TV and the camera facing the screen to read x-y mouse coordinates to shoot at.
* "QR-AR": With slight changes to the low- and mid- layers it seems we can find the positioning parts of QR codes - when they use circle shapes instead of cube shapes.

We are basically not using any dependencies for 1-3 implementation levels and provide a very simple API for the most broad use cases. No OpenCV or heavyweight libraries are needed to integrate the results for 2D marker tracking into a 3rd party product, but basically just include-ing the header-only libraries. This was actually a serious design goal! Despite this, for the ease of develpment, the provided unit tests are using CImg to manipulate images for testing layer 1-3 and example use cases for the above mentioned scenarios might of course use different frameworks or APIs - like v4l2 for realtime streaming performance testing, opengl to show the results of realtime tests and OpenGV for trying out various algorithms for getting projection matrices or the camera translation data using PnP (Persepective-n-Problem) solutions.

The text will be deliberately in Hungarian, but the code should be well documented in english and there will be some technical descriptions on the "turul" project page on github. Everything will be of course completely open source forever ;-)

### Technological description of the text template I am using

Markdown template for thesis works in the Budapest Eötvös Lóránd university. **This is an experimental work** and is only recommended for users experienced with _both Markdown and LaTeX_ - or crazy people such as myself.

Forked from a BME template with very similar goals and a nice structure.
Tested on Ubuntu Linux 16.04 with pandoc 1.16.0.2 and texlive (1.2).

### Requirements

* Pandoc 1.12.4.2 with pandoc-citeproc (see http://johnmacfarlane.net/pandoc/installing.html#all-platforms). Ubuntu 14.04 only provides version 1.12.2.1 which does not produce proper cross references in the HTML output. I am doing my testing with 1.16.0.2 at this time because that is the version I can readily apt-get on my good old 16.04 Ubuntu laptop.
* TeX Live (I have found out that `texlive-full` is not necessary! You can use texlive-base and then use tlmgr to get missing stuff)

### Troubleshooting

After trying this on the 16.04 and the named software version I have found myself with a lot of errors:

* TexLive complained about missing components because (I think that is the reason) I was only using texlive-base and not the full 2Gb pack
* For getting those packages I tried tlmgr but that failed miserably and forums wrote a lot of weird things about it being a bug in ubuntu. This have solved it however: https://tex.stackexchange.com/questions/137428/tlmgr-cannot-setup-tlpdb
* magyar.ldf file was missing so I downloaded one from the BME Latex pages (now it is included in this git repo and tex finds it like this)
* There was some weird error in chapter04.tex: It complained about a single quote mark or something so I looked up the problematic place and just removed the text around it as a quickfix. You can see my change in the git commit so you will not find the same stuff but worth mentioning there was this problem. It seems there is nothing in there I would need for myself so I just ignore this...

### Usage

* Clone this repository:
* Use `make all` `make pdf`, `make html`, `make epub` to generate the thesis in your desired output format.

Rem.: Mostly I only test pdf however because I do not have endless time ;-)
