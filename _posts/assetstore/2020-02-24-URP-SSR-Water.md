---
layout: post
title: "LWRP/URP SSR Water"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## LWRP/URP SSR Water

This is the **LWRP/URP** version of [Fatanstic SSR Water](https://assetstore.unity.com/packages/vfx/shaders/fantastic-ssr-water-154020?aid=1101l85Tr).

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

## How to use

After importing the package, you'll see the folders listed like this:

![](/img/urp-ssr-water/screenshot4.png)

**ForwardSSRWater_Common** contains common resources such as wave textures and skybox.

**ForwardSSRWater_LWRP** is the version of **LWRP**, **ForwardSSRWater_URP** is the version of **URP**, choose the one you need and delete the other one.

Shader is named like this:

| render-pipeline | shader name |
| ---- | ---- |
| LWRP | BadDog/LWRP/BGWater |
| URP | BadDog/URP/BGWater |

To run the shader correctly, each **RenderPipelineAsset** should toggle **Depth Texture** and **Opaque Texture**:

![](/img/urp-ssr-water/screenshot5.png)

That's all, you can check the demo scenes, and it should work, :)

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

Refaction needs **Opaque Texture** enabled.
![](/img/urp-ssr-water/screenshot11.png)

GrabTexture's uv is distorted by wave normal, and you can adjust the final **distort scale**.

#### IBL and SSR

![](/img/urp-ssr-water/screenshot12.png)

Unity's reflection probe is used for **IBL**, but it's not enough.
If you need a **realistic realtime reflection**, you can enable **screen space reflection**.
IBL and SSR are **mixed** for the final enviroment lighting. 

SSR **Sample Count** is performance sensitive. For mobile device, max sample count use 8 and sample step use 20 is good enough.

#### Final

The final water color is mixed by reflection and refraction. 

## About the examples

There are four example scenes, show you how to adjust the shader's properties.

+ testSSR
+ testLighting
+ testDepthAndMuddy
+ testRoom

You can check them for details.

**LWRP version** is tested using unity **2019.1** and unity **2019.2**.

**URP version** is tested using unity **2019.3**.

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |

