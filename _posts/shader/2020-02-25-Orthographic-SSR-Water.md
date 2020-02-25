---
layout: post
title: "SSR Water For Orthographic Camera"
subtitle: ""
author: "Bad Fat Dog"
header-mask: 0.2
catalog: true
tags:
  - Plan
---

## SSR Water For Orthographic Camera

| [Fantastic SSR Water](https://assetstore.unity.com/packages/vfx/shaders/fantastic-ssr-water-154020?aid=1101l85Tr) | [LWRP/URP SSR Water](https://assetstore.unity.com/packages/vfx/shaders/lwrp-ssr-water-155402?aid=1101l85Tr) |

One review:

> A good asset if you use perspective camera. Unfortunately it doesn't work correctly with orthographic one which I use in my project.

Oh，I forgot **orthographic camera**, I should support it.

## How To

For orthographic camera, the calculation of **WorldViewDirection** and **Depth** is quite different.

#### WorldViewDirection

For perspective camera:

```
lightingData.worldViewDir = normalize(_WorldSpaceCameraPos.xyz - lightingData.worldPos);
```

For orthographic camera:

```
lightingData.worldViewDir = normalize(UNITY_MATRIX_V[2].xyz);
```

For both:

```
lightingData.worldViewDir = unity_OrthoParams.w * UNITY_MATRIX_V[2].xyz + (1- unity_OrthoParams.w) * (_WorldSpaceCameraPos.xyz - lightingData.worldPos);
```

#### Depth

For perspective camera, I get scene depth like this:

```
float sceneDepth = LinearEyeDepth(SAMPLE_DEPTH_TEXTURE(_CameraDepthTexture, sampler_CameraDepthTexture, screenMatchUVZ.xy), _ZBufferParams);
```

Above code does not work for orthographic camera, I should write like this:

```
inline float GetOrthoDepthFromZBuffer (float rawDepth) 
{
    #if defined(UNITY_REVERSED_Z)
        #if UNITY_REVERSED_Z == 1
            rawDepth = 1.0f - rawDepth;
        #endif
    #endif

    return lerp(_ProjectionParams.y, _ProjectionParams.z, rawDepth);
}
```

```
float rawDepth = SAMPLE_DEPTH_TEXTURE(_CameraDepthTexture, sampler_CameraDepthTexture, screenMatchUVZ.xy);
float perspectiveSceneDepth = LinearEyeDepth(rawDepth, _ZBufferParams);
float orthoSceneDepth = GetOrthoDepthFromZBuffer(rawDepth);
return lerp(perspectiveSceneDepth, orthoSceneDepth, unity_OrthoParams.w);
```

When computing depth from the result of **TransformWorldToHClip**, the situation is similar.

My local shader works well for orthographic camera now:

![](/img/ssr-water-fix/screenshot1.png)

I'll commit the new version soon.

## Reference

I've learned a lot from [Lux URP/LWRP Essentials](https://assetstore.unity.com/packages/vfx/shaders/lux-urp-lwrp-essentials-150355?aid=1101l85Tr), it's really a great asset.

