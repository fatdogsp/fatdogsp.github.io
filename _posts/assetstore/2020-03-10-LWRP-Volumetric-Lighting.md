---
layout: post
title: "LWRP Volumetric Lighting"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## LWRP Volumetric Lighting

![](/img/volumetric-lighting/screenshot1.png)
![](/img/volumetric-lighting/screenshot2.png)
![](/img/volumetric-lighting/screenshot3.png)
![](/img/volumetric-lighting/screenshot4.png)

**LWRP Volumetric Lighting** is the **LWRP** version of [Fast Volumetric Lighting](https://assetstore.unity.com/packages/vfx/shaders/fullscreen-camera-effects/fast-volumetric-lighting-152973?aid=1101l85Tr&pubref=BGVL).

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

1. Install **unity 2019** and **LWRP** related packages, then import **LWRP Volumetric Ligthing** asset. (All demos have been tested using **Unity 2019.1** and **2019.2**. **Unity 2018** is not tested yet, but i think it **will work well** too, just try it).

    ![](/img/volumetric-lighting/screenshot5.png)

2. Make sure all **LWRP** related packages are all installed, including **Unity's Post-processing Stack v2**, which installed with **LWRP** by default.

    ![](/img/volumetric-lighting/screenshot6.png)

3. Assign **LightweightRenderPipelineAsset** to Graphics **Scritable Render Pipeline Settings** slot,  you can choose my pipeline asset under **Examples/Settings** folder or create your own.

    ![](/img/volumetric-lighting/screenshot7.png) 

4. Add **BGMainLight** component to the light source which you need light casting. **Multi light** is also supported, if you need more than one light to cast, each light needs a **BGMainLight**.

    ![](/img/volumetric-lighting/screenshot8.png) 
    
5. Add **Post Process Layer** to your main camera, and you will see **BGVolumetricLighting** below **Custom Effect Sorting** section.

    ![](/img/volumetric-lighting/screenshot9.png) 
    
6. Add **Post Process Volume** to your volume gameobject, click **Add effect...** button and choose **BGVolumetricLighting**.

    ![](/img/volumetric-lighting/screenshot10.png) 

7. Adjust **Lighting Parameters** using **BGMainLight** component for each light, you can set the light color, light range, light intensity and so on. 

8. Adjust **Quality Parameters** using **BGVolumetricLighting** for global lighting quality. Quality Parameters are performance sensitive, check **About performance** section for more details.

9. Optional, add other Unity's **post processing effects** like **Bloom** or **ColorGrading** for better image effect, **BGVolumetricLighting** is done **ahead of** them. 

    ![](/img/volumetric-lighting/screenshot11.png) 
    
10. When light is in your camera's view, volumetric lighting will occur, that' all.

## About performance

1. **Quality Params Area** shows the parameters which are perfermance sensitive.

2. For mobile devices, you need fewer BGMainLight component(**<=2**), smaller Render Texture(**<=512**), fewer sample count(**<= 12**), and **2-3** blur count. You will get good quality with acceptable perfermance.

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

Enjoy it!

## About the limit

**Radial Blur** is fast, but it requires light source inside or not far away from your screen, check [The limit of radial blur](https://youtu.be/W-jEvyuJxAQ) before you buy it. 

The video uses [The Illustrated Nature](https://assetstore.unity.com/packages/3d/vegetation/the-illustrated-nature-153939?aid=1101l85Tr) as the example.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |




























