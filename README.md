# SFML Example and Visual Studio 2022

## Visual C++ 15 (2017) - 32-bit

https://www.sfml-dev.org/tutorials/2.5/start-vc.php

## Introduction

This tutorial is the first one you should read if you're using SFML with the Visual Studio IDE (Visual C++ compiler). It will explain how to configure your SFML projects.

## Installing SFML

First, you must download the SFML SDK from the download page. 

https://www.sfml-dev.org/download/sfml/2.5.1/

![start-vc-paths-](https://user-images.githubusercontent.com/98597119/217833693-98ce6824-a33a-46fe-b452-eabd0b23aef3.png)

You must download the package that matches your version of Visual C++. Indeed, a library compiled with VC++ 10 (Visual Studio 2010) won't be compatible with VC++ 12 (Visual Studio 2013) for example. If there's no SFML package compiled for your version of Visual C++, you will have to build SFML yourself.

You can then unpack the SFML archive wherever you like. Copying headers and libraries to your installation of Visual Studio is not recommended, it's better to keep libraries in their own separate location, especially if you intend to use several versions of the same library, or several compilers.

## Creating and configuring a SFML project

The first thing to do is choose what kind of project to create. It is recommended to select "Empty Project". The dialog window offers a few other options to customize the project: select "Console application" or "Windows application" only if you know how to use pre-compiled headers.
For the purpose of this tutorial, you should create a main.cpp file and add it to the project, so that we have access to the C++ settings (otherwise Visual Studio doesn't know which language you're going to use for this project). We'll explain what to put inside later.

Now we need to tell the compiler where to find the SFML headers (.hpp files), and the linker where to find the SFML libraries (.lib files).

In the project's properties, add:

The path to the SFML headers (<sfml-install-path>/include) to C/C++ » General » Additional Include Directories
The path to the SFML libraries (<sfml-install-path>/lib) to Linker » General » Additional Library Directories
These paths are the same in both Debug and Release configuration, so you can set them globally for your project ("All configurations").

![start-vc-paths](https://user-images.githubusercontent.com/98597119/217830003-4fc159a7-a282-4300-ae81-00cedc7f2404.png)
  
The next step is to link your application to the SFML libraries (.lib files) that your code will need. SFML is made of 5 modules (system, window, graphics, network and audio), and there's one library for each of them. Libraries must be added in the project's properties, in Linker » Input » Additional Dependencies. Add all the SFML libraries that you need, for example "sfml-graphics.lib", "sfml-window.lib" and "sfml-system.lib".

## Additional Dependencies - Debug - Win32

sfml-graphics-d.lib;sfml-window-d.lib;sfml-system-d.lib;sfml-audio-d.lib;sfml-network-d.lib;freetype.lib;winmm.lib;gdi32.lib;openal32.lib;flac.lib;vorbisenc.lib;vorbisfile.lib;vorbis.lib;ogg.lib;ws2_32.lib;%(AdditionalDependencies)
  
## Additional Dependencies - Release - Win32  

sfml-graphics.lib;sfml-window.lib;sfml-system.lib;sfml-audio.lib;sfml-network.lib;freetype.lib;winmm.lib;gdi32.lib;openal32.lib;flac.lib;vorbisenc.lib;vorbisfile.lib;vorbis.lib;ogg.lib;ws2_32.lib;%(AdditionalDependencies)

![start-vc-link-libs](https://user-images.githubusercontent.com/98597119/217830961-9b1583d6-e9bc-464d-ad12-736e21b57876.png)
  
## Project Folders 

* Copie all dll in C:\SFML-2.5.1\bin to project folder.

Eg:
  
![libs](https://user-images.githubusercontent.com/98597119/217836369-aa79ab26-e042-4fce-95e1-d4e543d8e4e2.png)  
