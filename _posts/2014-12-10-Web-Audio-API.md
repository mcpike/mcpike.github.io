---
layout: post
title: Using the Web Audio API to analyze audio  
tags: javascript web-audio 
---

## The Goal

Working on a project recently, it seemed that most of the available tutorials that I found that were related to the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) were out of date and/or broken.

I just wanted to provide a resource with a currently (as of Dec. 2014) working sample for a basic setup with an analyser node.

The following section is the setup for routing Audio to the visualizer:

## The Process

There are 5 general steps:

  1. Create audio context
  2. Inside the context, create sources — such as &lt;audio&gt;, oscillator, stream
  3. Create effects nodes, such as reverb, biquad filter, panner, compressor
  4. Choose final destination of audio, for example your system speakers
  5. Connect the sources up to the effects, and the effects to the destination.

For more information, see [here](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext)

The example below assumes that you have a &lt;audio&gt; tag on your HTML page which you want to use as a source. If you would prefer to use another source, you can find the various input options [here](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API#Creating_an_audio_source)

## The Code


{% highlight javascript %}

// 1. Create audio context, see: https://developer.mozilla.org/en-US/docs/Web/API/AudioContext
var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

// 2. Inside the context, create sources
var audio  = document.querySelector('audio'); // creating a reference to the <audio> tag
var source = audioCtx.createMediaElementSource(audio);

// 3. Create effects nodes
var analyser = audioCtx.createAnalyser();

// 4. Choose final destination of audio
analyser.connect(audioCtx.destination);

// 5. Connect the sources up to the effects
source.connect(analyser);

{% endhighlight %}


## The Follow Up

From here you:

 1. Set the [FFT](http://en.wikipedia.org/wiki/Fast_Fourier_transform) value
 2. Create a buffer
 3. Create a data array
 4. Filter the data by Frquency and/or Time Domain
 5. Pass the data to your visualizer

Check out [AnalyserNode](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) for details.


