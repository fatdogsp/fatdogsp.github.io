---
layout: post
title: "The Pretty Girls"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

## The Pretty Girls

![](/img/the-pretty-girls/screenshot1.png)

![](/img/the-pretty-girls/screenshot2.png)

![](/img/the-pretty-girls/screenshot3.png)

This is a collection of stylized eastern girls. 

The package contains **1 basic skin** with **4 body models**, **4 hair models** and **2 weapons**. 

**Customzied shaders** are supplied and used for stylized rendering. There are **1 body shader** and **2 hair shaders**.

Body meshes are about **7000-10000** triangles, weapon meshes are about **1200-1300** triangles, hair meshes are about **3000-4000** triangles.

Most body textures are **1024 x 1024**, including diffuse texture, normal map, mix texture(combined pbr and skin). Most hair textures and weapon textures are **512 x 512**, including diffuse texture, normal map, mix texture.

The models are **rigged**, **3 generic animations** (idle, guard, guard_to_idle) are supplied. Body bones which named "**Ribbon_xxx**" and hair bones are prepared for **physics**, you can add [Dynamic Bones](https://assetstore.unity.com/packages/tools/animation/dynamic-bone-16743?aid=1101l85Tr) to make them move.

Furthermore, **a simple avatar system** is supplied, which shows how to **put these models together** and **change clothes**.

---

## About the shaders

#### BadDog/BGStandard

![](/img/the-pretty-girls/screenshot4.png)

**BGStandard** is used by **body and weapon**. MixTex's g channel can determine if it is a skin. 

Non-skin rendering is similar to Unity's standard shader. 

Skin rendering use **SSS Lut** as the lookup texture for diffuse lighting, MixTex's b channel is the **curvature**.

#### BadDog/BGStandardHair

![](/img/the-pretty-girls/screenshot5.png)

**BGStandardHair** is used by **hair**. MixTex's g channel can determine if it is a hair.

Non-hair rendering is similar to Unity's standard shader. 

Hair rendering is stylized, hair diffuse color is mixed with **Hair Base Color** and **Hair Mix Color**, MainTex's r channel and g channel can determine the two color's weight. 
Hair uses tangent for **anisotropic specular** lighting, and **two specular layers** can be adjusted. 

#### BadDog/BGHair

![](/img/the-pretty-girls/screenshot6.png)

**BGHair** is used by **pure hair**. 

When MixTex's g channel is all hair, you can choose **BGHair** instead of **BGStandardHair** to save perfermance, and MixTex is not needed for **pure hair**.

---

## About BGAvatar and Change Clothes

You can find a demo scene called **testChangeCloth** which shows how to put these models together and **change clothes**.

![](/img/the-pretty-girls/screenshot7.png)

![](/img/the-pretty-girls/screenshot8.png)

Drag **BaseSkin** prefab to your scene, you can find a naked girl with **full bones**, and three subparts: **Body, Face, MainWeapon**.

![](/img/the-pretty-girls/screenshot9.png)

![](/img/the-pretty-girls/screenshot10.png)

You can find **BGAvatar** component attached, **Root Bone**, **Base Body**, **Base Weapon** and **Hair Mount Point** slots are assigned.

![](/img/the-pretty-girls/screenshot11.png)

Drag **BGSubpartManager** prefab to your scene, then you will find all subparts the package contains.

![](/img/the-pretty-girls/screenshot12.png)

Now if you want to change body to **Body_02**, check **Body_02**'s element index in **BGSubpartManager**'s body list, assign the index to **BGAvatar**'s **Default Body Index** slot, then body will be changed.

![](/img/the-pretty-girls/screenshot13.png)

![](/img/the-pretty-girls/screenshot14.png)

![](/img/the-pretty-girls/screenshot15.png)

Weapon and hair can be changed by the same way, and hair will be mounted to **Hair Mount Point**.

You can change pose to check if **BGAvatar** works correctly.

![](/img/the-pretty-girls/screenshot16.png)

---

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |




























