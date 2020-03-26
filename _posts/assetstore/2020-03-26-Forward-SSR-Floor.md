---
layout: post
title: "Forward SSR Floor"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## Forward SSR Floor

This is the **Standard RP** version of **Forward SSR Floor**.

![](/img/forward-ssr-floor/screenshot1.png)

![](/img/forward-ssr-floor/screenshot2.png)

![](/img/forward-ssr-floor/screenshot3.png)

## Features

+ Physically correct, support metallic and smoothness.
+ Combine screen space reflection with Unity's indirect specular.
+ Support realtime lighting and lightmap.
+ Adjustable properties for SSR quality and performance.
+ Forward SSR, mobile ready.
+ Support normal map.

## How to use

+ **Forward SSR Floor** need camera's depth texture, so you should enable camera's depth mode or add my **CameraDepthToggle** component to your main camera.
+ Assign **BadDog/BGSSRFloor"** shader to your floor material, and that's all.

## Shader properties

![](/img/forward-ssr-floor/screenshot4.png)

#### MixMap

+ R: metallic
+ G: ambient occlusion
+ B: emission
+ A: smoothness

#### Screen Space Reflection

+ *SSR Max Ray Count*
	+ It controls the max reflected ray number for ray marching.
	+ For rough floor, you need more rays(**>=3**) to get better quality. 
	+ For smooth floor, **1-2** rays is enough.
	+ It's performance sensitive, for mobile device, it should be **<= 3**.
+ *SSR Max Sample Count* and *SSR Sample Step*
	+ Ray marching distance is controlled by **SSR Max Sample Count * SSR Sample Step**.
	+ For better quality, you need higher *SSR Max Sample Count* and smaller *SSR Sample Step*. 
	+ *SSR Max Sample Count* is performance sensitive, for mobile device, it should be **<= 10**.
+ *SSR Intensity*
	+ It controls the final SSR intensity.
+ *SSR Max Roughness*
	+ It controls the max roughness that reflects screen color.

## About the demo scenes

+ testLightmap
	+ Test ssr outdoor with lightmap.
+ testRoom
	+ Test ssr in a room.
+ testTransparent
	+ Test ssr with realtime lights and transparent particles.

All demo scenes need **Linear Space**.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |




























