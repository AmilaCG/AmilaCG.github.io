+++
date = '2025-09-06T16:30:28-04:00'
draft = false
title = 'Bicubic Interpolation Based Image Upscaling'
[params]
    math = true
+++
## Introduction
Upscaling an image, or resize an image to a larger resolution, is about filling missing pixels of the output image in a way that looks natural. If you ever zoomed in a photo and noticed it become blocky or blurry, you've seen what happens when upscaling is done poorly. Bicubic interpolation is a popular technique because it produces results that are both smooth and sharp, avoiding the blocky look of nearest-neighbor and the blurriness of bilinear methods.

The key idea is that bicubic interpolation doesn’t just look at a pixel and its immediate neighbors, it considers a wider 4×4 grid of surrounding pixels and uses clever math to create smoother transitions. In this post, we’ll dive into how bicubic interpolation works, explore the math behind it, and see why it remains a go-to method in image processing and computer graphics.

This is an inline \(a^*=x-b^*\) equation.

These are block equations:

\[a^*=x-b^*\]

\[ a^*=x-b^* \]

\[
a^*=x-b^*
\]

These are also block equations:

$$a^*=x-b^*$$

$$ a^*=x-b^* $$

$$
a^*=x-b^*
$$
