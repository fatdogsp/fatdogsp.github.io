---
layout: post
title: "Simple Face Makeup"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - My Assets
---

### Simple Face Makeup

![](/img/simple-face-makeup/screenshot1.png)

This is a **face makeup tool** used for [The Pretty Girls](https://assetstore.unity.com/packages/3d/characters/humanoids/the-pretty-girls-157964?aid=1101l85Tr).

You can **change makeup** easily, and there are **6 brow textures**, **6 cheek textures**, **6 eyeball textures**, **6 eye makeup textures**, **6 forehead textures**, **6 lip textures** for you to choose.

You can also adjust **face color**, face color and makeups are finally combined to **one texture** and rendered in **one drawcall**.

Furthermore, **a customized shader** is supplied for **face rendering**, which is also used by [The Pretty Girls](https://assetstore.unity.com/packages/3d/characters/humanoids/the-pretty-girls-157964?aid=1101l85Tr).

---

### How to use

You can find a demo scene **test.unity** in the examples folder which shows how to use the tool.

![](/img/simple-face-makeup/screenshot2.png)

#### BGFaceMakeupManager

Drag **FaceMakeupManager** prefab to your scene, and you will find **BGFaceMakeupManager** component attached.

It's a manager of all makeup textures used for different face parts. 

![](/img/simple-face-makeup/screenshot3.png)

And you have to specify the **start position** of the makeup texture relative to **face base texture**.

For example, check the eyeball's start position: **0, 80**，it's the **left bottom** position of the **face base texture**. 

![](/img/simple-face-makeup/screenshot4.png)

#### BGFaceMakeup

Add **BGFaceMakeup** component to face renderer, and then we can adjust the makeup.

![](/img/simple-face-makeup/screenshot5.png)

We can adjust **face color** and **6 makeup parts** of the face: brow, eyeball, eye makeup, cheek, forehead and lip.

For example, if we want to change lip texture to **FaceMakeupManager**'s lip **Element 4**, then we set **BGFaceMakeup**'s **Default Lip Index** to **4**, and it will work.

#### Makeup Texture

The face base texture and the makeup texture need **read/write enabled** toggled.

And if you adjust base texture's size, you should also adjust makeup texture's size and readjust the start position.

Makeup texture's alpha channel is used as a mask.

![](/img/simple-face-makeup/screenshot6.png)

![](/img/simple-face-makeup/screenshot7.png)

Only white area can be applied to base texture.

---

## About the shader

The shader **BadDog/BGStandard** is used for face rendering.

Check [The Pretty Girls](https://fatdogsp.github.io/2020/03/08/The-Pretty-Girls/) for details.

---

## Customer Support:

| email | web |
| ---- | ---- |
| shenpan998@gmail.com |  [https://fatdogsp.github.io/2020/02/20/My-Assets/](https://fatdogsp.github.io/2020/02/20/My-Assets/) |









































