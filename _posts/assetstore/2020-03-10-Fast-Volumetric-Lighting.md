---
layout: post
title: "Fast Volumetric Lighting"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## Fast Volumetric Lighting

![](/img/volumetric-lighting/screenshot1.png)
![](/img/volumetric-lighting/screenshot2.png)
![](/img/volumetric-lighting/screenshot3.png)
![](/img/volumetric-lighting/screenshot4.png)

**Fast Volumetric Lighting** is a fast and high quality volumetric lighting implematation based on **Radial Blur**.

[Youtube](https://youtu.be/f2eAI2nG1BU)

If you need a **LWRP/URP** version, check [LWRP/URP Volumetric Lighting](https://assetstore.unity.com/packages/vfx/shaders/fullscreen-camera-effects/lwrp-volumetric-lighting-155676?aid=1101l85Tr).

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

## How to use

1. Add **BGMainLight** component to every light that you want to cast volumetric lighting.
 
    ![](/img/fast-volumetric-lighting/screenshot2.png)  

2. Add **BGVolumetricLighting** component to your main camera. **BGVolumetricBehavior** will be added automaticly when **BGVolumetricLighting** is added..

    ![](/img/fast-volumetric-lighting/screenshot3.png) 

3. Adjust **BGMainLight's Lighting Parameters** for each light to set light color, light range, light intensity and so on. 

4. Adjust **BGVolumetricLighting's Quality Parameters** for global lighting quality.

5. When the light source is in your camera's view, volumetric lighting will occur.

## About performance

1. Check **BGVolumetricLighting's Quality Area**, it shows the parameters which are perfermance sensitive.
2. For mobile devices, you need fewer BGMainLight(**<=2**), smaller Render Texture(**<=512**), fewer sample count(**<= 12**), and **2-3** blur count. You will get good quality with acceptable perfermance.
3. The effect is auto disabled when all lights are **out of view** to save more perfermance.

## About the examples

There are 5 example scenes.
1. testPC
2. testMobile
3. testNight
4. testOutdoor
5. testMultiLight

Demo scenes include **day and night, indoor and outdoor, pc and mobile, one light casting and multi light casting**, you can check the difference between their **Lighting Params** and **Quality Params**.

To run these demos correctly, you should set Unity's color space to **Linear**. If you are using Gamma Space, you need readjust **Lighting Params** yourself. 

If you are using Unity's PostProcessing Stack, please make sure that **Fast Volumetric Lighting** is executed first.

## About the limitation

**Radial Blur** is fast, but it requires light source inside or not far away from your screen, check [The limitation of radial blur](https://youtu.be/W-jEvyuJxAQ) before you buy it. 

The video uses [The Illustrated Nature](https://assetstore.unity.com/packages/3d/vegetation/the-illustrated-nature-153939?aid=1101l85Tr) as the example.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |




























