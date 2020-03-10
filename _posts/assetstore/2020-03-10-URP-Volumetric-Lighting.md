---
layout: post
title: "LWRP/URP Volumetric Lighting"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## LWRP/URP Volumetric Lighting

![](/img/volumetric-lighting/screenshot1.png)
![](/img/volumetric-lighting/screenshot2.png)
![](/img/volumetric-lighting/screenshot3.png)
![](/img/volumetric-lighting/screenshot4.png)

**LWRP/URP Volumetric Lighting** is the **LWRP/URP** version of [Fast Volumetric Lighting](https://assetstore.unity.com/packages/vfx/shaders/fullscreen-camera-effects/fast-volumetric-lighting-152973?aid=1101l85Tr&pubref=BGVL).

[Youtube](https://youtu.be/6v_wtVz6bbQ)

**Fast Volumetric Lighting** is a fast and high quality volumetric lighting implematation based on **Radial Blur**. 

## Features

+ Multi light casting.
+ Dynamic.
+ Customized lighting parameters and quality parameters.
+ Optimized for mobile, really fast.
+ Debuggable.
+ Support HDR.
+ PC && mobile examples supplied.
+ Indoor && outdoor examples supplied.
+ One light && multi light examples supplied.

## How to use?

1. **LWRP** version is based on **Post Processing Stack V2**, and **URP** version is based on **SRP's Renderer Features**. The document is for **URP**, if you are interesting in **LWRP** version, please check [LWRP-Volumetric-Lighting's Document](https://fatdogsp.github.io/2020/03/10/LWRP-Volumetric-Lighting/). 

2. **URP** version requires Unity 2019.3 and above, you need to install all **URP** related packages first.

	![](/img/volumetric-lighting/screenshot12.png)

3. Assign **UniversalRenderPipelineAsset** in graphic settings. Check **Assets/BadDog/VolumetricLighitng_URP/Settings** folder, there are two predefined pipeline assets, one is for PC, the other is for mobile.

	![](/img/volumetric-lighting/screenshot13.png)

4. Check each **UniversalRenderPipelineAsset_Renderer**, and you will find **BGVolumetricLighting** Renderer Features, it's my Volumetric Lighitng, it's executed before URP's Post Processing.

	![](/img/volumetric-lighting/screenshot14.png)

5. Add **BGMainLight** component to the light source which you need light casting. **Multi light** is also supported, if you need more than one light to cast, each light needs a **BGMainLight**.

    ![](/img/volumetric-lighting/screenshot8.png) 

6. Now everything is ready, volumetric lighting will occur when the light source is in your camera’s view, check the demo scenes for more details.

## About performance

1. For mobile devices, you need fewer BGMainLight component(**<=2**), smaller Render Texture(**<=512**), fewer sample count(**<= 12**), and **2-3** blur count. You will get good quality with acceptable perfermance.

2. The effect is auto disabled when all lights are **out of view** to save more perfermance.

## About the examples

There are 5 example scenes.
1. testPC
2. testMobile
3. testNight
4. testOutdoor
5. testMultiLight

Demo scenes include **day and night, indoor and outdoor, pc and mobile, one light casting and multi light casting**, you can check the difference between their **Lighting Params** and **Quality Params**.

To run these demos correctly, you should set Unity's color space to **Linear**. If you are using Gamma Space, you need readjust **Lighting Params** yourself. 

Enjoy it!

## About the limit

**Radial Blur** is fast, but it requires light source inside or not far away from your screen, check [The limit of radial blur](https://youtu.be/W-jEvyuJxAQ) before you buy it. 

The video uses [The Illustrated Nature](https://assetstore.unity.com/packages/3d/vegetation/the-illustrated-nature-153939?aid=1101l85Tr) as the example.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |




























