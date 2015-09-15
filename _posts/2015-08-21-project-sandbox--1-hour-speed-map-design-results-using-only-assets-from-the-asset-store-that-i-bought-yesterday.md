---
layout: post
title: Project Sandbox, 1 hour Speed Map Design Results, using only Assets from the asset store. A conclusion of what I learned.
categories: ['personal blog']
tags: ['unity']
published: True
---

<iframe src="https://www.youtube.com/embed/03OEpFUg-7U" frameborder="0" allowfullscreen></iframe>

---
What I learned from this project was that, screen-space-reflection is actually super hard to use. As you see in the first part of the video or `PHASE`, I was actually tilting the camera in every angle possible to get the reflection to work right; The problem is because it's screenspace, faces and angles that are not facing to the camera is not rendered because of culling. So Basically no other angle work well for open spaces exposed directly to the sky except 0° sadly.

The other thing I learned is that unity terrain really does suck a bit, so limited, so little options to create anything creative other then curvy lines. I used the Unreal Terrain editor a long time ago so I have no idea what I'm missing out, but I did not have much fun with the one in Unity.
