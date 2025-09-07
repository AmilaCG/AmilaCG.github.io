+++
date = '2025-09-06T16:30:28-04:00'
draft = true
title = 'Bicubic Interpolation Based Image Upscaling'
[params]
    math = true
+++
Upscaling an image, or resize an image to a larger resolution, is about filling missing pixels of the output image in a way that looks natural. If you ever zoomed in a photo and noticed it become blocky or blurry, you've seen what happens when upscaling is done poorly. Bicubic interpolation is a popular image scaling technique because it produces results that are both smooth and sharp, avoiding the blocky look of nearest-neighbor and the blurriness of bilinear methods.

The key idea is that bicubic interpolation doesn’t just look at a pixel and its immediate neighbors as nearest-neighbor and bilinear methods, it considers a wider 4×4 grid of surrounding pixels and uses clever math to create smoother transitions. In this post, we’ll dive into how bicubic interpolation works, explore the math behind it, and see why it remains a go-to method in image processing and computer graphics.

| Native | Nearest (x4) | Bilinear (x4) | Bicubic (x4) |
|--------|--------------|---------------|--------------|
| ![Native](/images/bicubic-interpolation/native.png) | ![Nearest](/images/bicubic-interpolation/nearest_x4.png) | ![Bilinear](/images/bicubic-interpolation/bilinear_x4.png) | ![Bicubic](/images/bicubic-interpolation/bicubic_x4.png) |

{{< credit >}}
By James Petts / shaddim - Cropped from 
<a href="//commons.wikimedia.org/wiki/File:Green_sea_shell_(11985932994).jpg" title="File:Green sea shell (11985932994).jpg">Green sea shell (11985932994).jpg</a>, 
<a href="https://creativecommons.org/licenses/by-sa/2.5" title="Creative Commons Attribution-Share Alike 2.5">CC BY-SA 2.5</a>, 
<a href="https://commons.wikimedia.org/w/index.php?curid=47847740">Link</a>
{{< /credit >}}