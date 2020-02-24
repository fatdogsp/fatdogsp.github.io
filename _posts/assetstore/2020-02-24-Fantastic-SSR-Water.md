---
layout: post
title: "Fatanstic SSR Water"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## Fantastic SSR Water

![](/img/urp-ssr-water/screenshot1.png)

![](/img/urp-ssr-water/screenshot2.png)

![](/img/urp-ssr-water/screenshot3.png)

[Youtube](https://youtu.be/8KtdqC4iNH4)

## Features

+ Three direction realistic waves.
+ Support clean and muddy.
+ PBR lighting with screen space reflection.
+ Realistic refraction.
+ Forward SSR, mobile ready.

### How to use

+ SSR water need **camera depth texture**, so you should enable depth mode or just add **"CameraDepthToggle"** component to your main camera.
+ Assign **"BadDog/BGWater"** shader to your water material, then assgin the material to your water plane. 
+ Adjust material parameters, and that's all.

## Shader properties

#### Wave Section

![](/img/urp-ssr-water/screenshot6.png)

**Two** wave maps generate three direction waves. You can adjust each wave's **tiling** and **offset**.

#### Water Base Color 

![](/img/urp-ssr-water/screenshot7.png)

It's computed as **diffuse color**.

#### Water Muddy and Depth

![](/img/urp-ssr-water/screenshot8.png)

Water can be **clean** or **muddy**. Clean water is more transparent than muddy water.
Water's transparency is computed by **depth**.  
Depth is computed by **muddy scale** and camera's **view direciton**, you can also add a **depth offset** to adjust the final transparency.

#### Specular

![](/img/urp-ssr-water/screenshot9.png)

Specular color is always **(0.04, 0.04, 0.04)**, and you can adjust it's intensity as you need.

#### Refraction

![](/img/urp-ssr-water/screenshot10.png)

Refaction needs Unity's grab pass. GrabTexture's uv is distorted by wave normal, and you can adjust the final distort scale.

#### IBL and SSR

![](/img/urp-ssr-water/screenshot12.png)

Unity's reflection probe is used for **IBL**, but it's not enough.
If you need a **realistic realtime reflection**, you can enable **screen space reflection**.
IBL and SSR are **mixed** for the final enviroment lighting. 

SSR **Sample Count** is performance sensitive. For mobile device, max sample count use 8 and sample step use 20 is good enough.

#### Final

The final water color is mixed by reflection and refraction. 

## About the examples

There are four example scenes:

+ testSSR
+ testLighting
+ testDepthAndMuddy
+ testRoom

Choose **linear space** and check them for details.

All demos are tested using unity 2017, 2018 and 2019.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |

