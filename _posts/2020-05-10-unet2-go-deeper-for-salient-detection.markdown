---
layout: post
---

<https://github.com/NathanUA/U-2-Net>

Use unet for detect salient object for background removal.
It is a very interesting when they release a model is only 4MB.

The use of U-Net, a network for semantic segmentation, is for saliency detection.

It is a good idea because of similar in problem semantic segmentation and saliency detection.

There is another classic solution for saliency such as [DRFI](https://github.com/playerkk/drfi_cpp). That works very well in my 
experience.

But for now, we could see U-Net, a deep-learning solution, applied with very good result.

U-Net network architecture review:
- Including encoding and decoding part.
- Encoding: Use convolution layer, then down-sampling 1/2.
- Decoding: Use deconvolution layer , concat with convolution layer, then up-sampling * 2

