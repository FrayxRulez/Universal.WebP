# WebP decoder for Universal Windows Platform

Introduction
============
This repository contains a Windows Runtime Component that wraps up [libwebp] and allows to decode static and animated WEBP images. Wrapper code is mostly based on Facebook's [Fresco] library for Android.

The code is released under the MIT/X11, so feel free to modify and share your changes with the world.

How to
======
You can use `WebPImage.DecodeFromByteArray` method to get a `WriteableBitmap` directly from a static WEBP.

If you want to decode an animated WEBP (or you need to decode both) you can use instead `WebPImage.CreateFromByteArray`.
This method returns a reference to a `WebPImage` object instance that exposes an array of `WebPFrame`s via its `Frames` property. 

You can simply loop the collection and get a `WriteableBitmap` from every frame using its `RenderFrame` method.

Install
=======
You can install the library via [NuGet].

###Install-Package [Universal.WebP]

[libwebp]:https://developers.google.com/speed/webp/
[Fresco]:https://github.com/facebook/fresco/blob/master/imagepipeline/src/main/jni/webpimage/webp.cpp
[NuGet]:http://nuget.org/
[Universal.WebP]:http://www.nuget.org/packages/Universal.WebP
