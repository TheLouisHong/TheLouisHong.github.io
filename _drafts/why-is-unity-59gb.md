---
layout: post
title: Why is Unity 5.9GB you ask?
categories: ['personal blog']
tags: []
published: True

---

The Unity Editor 5.9 GB *when installed*. Do you know what takes up all that space? My school has a proprietary game engine and it's install file is 13 MB.

Well I took WinDirStat and scanned the installed directory. Here's the results.

![WinDirStats visualized unity install dir][WinDirStatsVisual]

## The Largest Files

As you can see. These blue files with the extension of `.a` is taking up 35.2% which is 2.1 GB of everything. 

- libiPhone-lib-il2cpp-dev.a (473,4 MB)
- libiPhone-lib-il2cpp.a (444.9 MB)
- libiPhone-lib-i386-il2cpp.a (389.2 MB)
- libiPhone-lib-i386.a (382.3 MB)
- libiPhone-lib-dev.a (221.0 MB)
- libiPhone-lib.a (208.4 MB)

#### What is this extention?

> .a files are archives. They are groups of objects or static libraries and are also input into the linker. (It's used in C++) ([Stackoverflow][aFileRef])

#### What are these files? 

Well shocker, they're iPhone build compilers like the name suggests. The IL2CPP compiler is a special compiler build by Unity Techonlogies to compile intermediate languages that .NET languages compiles to and compiles it to C++. They do this because they want to leverage the large amount of C++ compilers out there. [Learn more in unity's blog.][IL2CPPBlog] The ones without i368 are ARM64 versions, and the ones with are the i368 version which is the 32bit version. The dev suffix is what unity use when you make an deveopment build, which enables development tools like the "Profiler" in Unity.

## The rest of the files.

Instead of writing paragraph for all of them, here's the labeled map.

[WinDirStatsVisual]: http://i.imgur.com/1N1MGdh.jpg
[aFileRef]: http://stackoverflow.com/questions/654713/o-files-vs-a-files
[IL2CPPBlog]: http://blogs.unity3d.com/2015/05/06/an-introduction-to-ilcpp-internals/