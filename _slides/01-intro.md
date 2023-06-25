---
layout: slides
title: Introduction to Bonsai
permalink: /slides/intro/
---

<section data-markdown data-separator="^\n---\n$" data-separator-vertical="^\n--\n$">
<script type="text/template">

![Bonsai](../../assets/images/bonsai-lettering.svg)

### Introduction to Bonsai
[neurogears.org/inc-2023](https://neurogears.org/inc-2023)
<table style="width: 100%;">
  <tr>
    <th style="vertical-align: middle; width: 50%; height: 100px; padding-left: 100px">
      <img alt="NeuroGEARS" src="../../assets/images/neurogears.svg"/>
    </th>
    <th style="vertical-align: middle; width: 50%; height: 100px; align: right">
      <img alt="Cajal" src="../../assets/images/cajal.png"/>
    </th>
  </tr>
</table>

---

### Outline

* Neuroscience Experiments and the Reactive Framework
* What is Bonsai?
* Core Concepts
* Demos
* Tutorial


---


<!-- .element: data-transition="default none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-1.svg)

--

<!-- .element: data-transition="none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-2.svg)

--

<!-- .element: data-transition="none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-3.svg)

--

<!-- .element: data-transition="none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-4.svg)

--

<!-- .element: data-transition="none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-5c.svg)

--

<!-- .element: data-transition="none" -->
### Neuroscience experiments and data streams
![Behavior Experiments](../../assets/images/behavior-experiments-5.svg)

---

<!-- .element: data-transition="default none" -->
#### The problem of multiple asynchronous data streams

```python
import cv2

camera0 = cv2.VideoCapture(1)
camera1 = cv2.VideoCapture(2)
while True:
   ret0, img0 = camera0.read()
   ret1, img1 = camera1.read()
   if (img0):
       cv2.imshow('img1',img0)
   if (img1):
       cv2.imshow('img2',img1)
```
<!-- .element: class="fragment" data-fragment-index="1" -->

--

<!-- .element: data-transition="none" -->
#### What is the problem?

 - Camera -> Tracking -> Log Data -> Camera -> Tracking -> Log Data -> Camera -> Tracking -> Log Data -> (...)

--

<!-- .element: data-transition="none" -->
#### What is the problem?

 - Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 -> Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 -> Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 (...)


--

<!-- .element: data-transition="none" -->
#### What is the problem?

 - Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 -> Nose Port value? -> If yes, Play Sound -> Log Nose port -> Acquire Microphone -> Log Microphone Data -> Acquire Ephys Data -> Log Ephys Data -> Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 -> (...) -> Nose Port value? -> If yes, Play Sound -> Log Nose port -> Acquire Microphone -> Log Microphone Data -> Acquire Ephys Data -> Log Ephys Data -> Camera1 -> Tracking1 -> Log Data -> Camera2 -> Tracking2 -> Log Data2 -> (...) -> Nose Port value? -> If yes, Play Sound -> Log Nose port -> Acquire Microphone -> Log Microphone Data -> Acquire Ephys Data -> Log Ephys Data

--

<!-- .element: data-transition="none" -->
#### Working with asynchronous data streams (just be "Reactive"...)

 - Camera1 -> Tracking1 -> Log Data
 - Camera2 -> Tracking2 -> Log Data2
 - Nose Port Value -> Log Nose Port
 - If Nose Port -> Play Speaker
 - Acquire Microphone -> Log Microphone Data
 - Acquire Ephys Data -> Log Ephys Data

---

<!-- .element: data-transition="default" -->
## Core Bonsai Designing Principles

- Handling asynchronous data streams and online processing
- Built of top of the Reactive Framework
- Quick and easy experimental prototyping
- Extensibility and modularity
- Open-source

---

## "Observable Sequences"


--


<!-- .element: data-transition="default none" -->
![Workflow](../../assets/images/graycam.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/graycam-marble.svg)
<!-- .element: class="fragment" style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="default none" -->
![Workflow](../../assets/images/graycam.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/graycam-marble-effects.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="default none" -->
![Workflow](../../assets/images/graycam.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/grayscaletransform.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="default none" -->
![Workflow](../../assets/images/framepicker-key.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/framepicker-marblecanvas.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="none" -->
![Workflow](../../assets/images/framepicker-sample.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/grayscalesample.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="none" -->
![Workflow](../../assets/images/framepicker-saveimage.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/saveimage.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

--

<!-- .element: data-transition="none" -->
![Workflow](../../assets/images/framepicker-saveimage.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->
![Marble diagram](../../assets/images/saveimagesink.svg)
<!-- .element: style="display: inline-block; vertical-align: middle;" -->

---

## The Bonsai Ecosystem


--

![Bonsai Ecosystem](../../assets/images/bonsai-packages.svg)

</script>
</section>

<!-- Raw HTML for embedded iframe backgrounds -->
<section data-background="#000000">
    <section data-background-iframe="https://www.youtube.com/embed/wwU6TzUJxNU?controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;loop=1&amp;playlist=wwU6TzUJxNU&amp;showinfo=0&amp;rel=0&amp;html5=1">
      <table style="height: 20%; margin-top: 65%; margin-left: -78px;">
        <tr><th>Gonçalo Lopes, Kampff Lab</th></tr>
      </table>
    </section>
    <section data-background-iframe="https://www.youtube.com/embed/qXqAXgXJPmo?controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;showinfo=0&amp;rel=0&amp;html5=1">
      <table style="height: 20%; margin-top: 65%; margin-left: -78px;">
        <tr><th>Lorenza Calcaterra, Kampff Lab</th></tr>
      </table>
    </section>
    <section data-background-iframe="https://www.youtube.com/embed/mJDV07ptQFk?start=40&amp;controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;showinfo=0&amp;rel=0&amp;html5=1">
      <table style="height: 20%; margin-top: 65%; margin-left: -78px;">
        <tr><th>George Dimitriadis, Kampff Lab</th></tr>
      </table>
    </section>
</section>

<section data-markdown data-separator="^\n---\n$" data-separator-vertical="^\n--\n$">
<script type="text/template">

#### Hardware synchronized acquisition & control
![Harp-Bonsai](../../assets/images/bonsai-harp.svg)

[harp-tech.org](https://harp-tech.org/)

</script>
</section>

<section>
  <h4>Next generation open ephys</h4>
  <img src="../../assets/images/nextgen-ephys.png" alt="ONI - Open Neuro Interface" width="500px" />
  <iframe src="https://www.youtube.com/embed/8xC404aTSUo?controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;loop=1&amp;playlist=8xC404aTSUo&amp;showinfo=0&amp;rel=0&amp;html5=1" width="400px" height="300px"></iframe>
  <a href="https://open-ephys.github.io/onix-docs/">open-ephys.github.io/onix-docs</a>
  <p>Jon Newman et al. @ Open-Ephys</p>
</section>

<section>
  <h4>Multi-fiber photometry recordings</h4>
  <img src="../../assets/images/bonsai-npm.svg" alt="Neurophotometrics" />
  <img src="https://github.com/neurophotometrics/neurophotometrics/wiki/images/calibrate-regions.gif" width="50%" alt="Neurophotometrics" />
  <a href="https://neurophotometrics.com/">neurophotometrics.com</a>
</section>

<section>
  <h4>Interactive visual environments</h4>
  <img src="../../assets/images/bonsai-bonvision.svg" alt="BonVision" />
  <img src="https://bonvision.github.io/assets/Images/Demos/DemoAR_v3.gif" width="50%" alt="Augmented Reality in BonVision" />
  <a href="https://bonvision.github.io/">bonvision.github.io</a>
  <p>Saleem Lab and Solomon Lab</p>
</section>

<!-- Raw HTML for embedded iframe backgrounds -->
<section>
  <h4>Real-time markerless pose estimation</h4>
  <img src="../../assets/images/bonsai-dlc.svg" alt="Bonsai-DeepLabCut" />
  <iframe src="https://www.youtube.com/embed/0aachcS0CUY?controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;loop=1&amp;playlist=0aachcS0CUY&amp;showinfo=0&amp;rel=0&amp;html5=1" width="500px" height="300px"></iframe>
  <a href="https://github.com/bonsai-rx/deeplabcut/">github.com/bonsai-rx/deeplabcut</a>
  <p>Mathis et al., Nat Neurosci, 2018</p>
</section>


<section>
  <h4>Multi-animal pose and identity tracking</h4>
  <img src="../../assets/images/bonsai-sleap.svg" alt="Bonsai-SLEAP" />
  <iframe src="https://www.youtube.com/embed/e3NDNKh_OoM?controls=0&amp;enablejsapi=1&amp;autoplay=1&amp;loop=1&amp;playlist=e3NDNKh_OoM&amp;showinfo=0&amp;rel=0&amp;html5=1" width="500px" height="300px"></iframe>
  <a href="https://bonsai-rx.org/sleap/">bonsai-rx.org/sleap</a>
  <p>Pereira et al., Nat Methods, 2022</p>
</section>

<section data-markdown data-separator="^\n---\n$" data-separator-vertical="^\n--\n$">
<script type="text/template">

![Bonsai](../../assets/images/bonsai-lettering.svg)

### Questions?
[neurogears.org/inc-2023](https://neurogears.org/inc-2023)
<table style="width: 100%;">
  <tr>
    <th style="vertical-align: middle; width: 50%; height: 100px; padding-left: 100px">
      <img alt="NeuroGEARS" src="../../assets/images/neurogears.svg"/>
    </th>
    <th style="vertical-align: middle; width: 50%; height: 100px; align: right">
      <img alt="Cajal" src="../../assets/images/cajal.png"/>
    </th>
  </tr>
</table>

</script>
</section>