+++
title = 'Image gallery and captions'
date = 2025-07-19T12:00:00+02:00
draft = true
tags = ['demo', 'images']
+++

This demo shows a responsive image gallery and captions with Markdown links.

## Gallery

{{< gallery label="Watch gallery" >}}

![Watch photo 1](https://yavuzceliker.github.io/sample-images/image-1021.jpg "Photo from [Yavuz Celiker's sample images](https://github.com/yavuzceliker/sample-images)")
![Watch photo 2](https://yavuzceliker.github.io/sample-images/image-1022.jpg "Second image with a [source link](https://github.com/yavuzceliker/sample-images)")
![Watch photo 3](https://yavuzceliker.github.io/sample-images/image-1023.jpg "Third image caption")

{{< /gallery >}}

The same caption syntax also works for a single image:

![Single watch photo](https://yavuzceliker.github.io/sample-images/image-1021.jpg "A single image with a [source link](https://github.com/yavuzceliker/sample-images)")

## Highlighted fragment

{{< highlight >}}

This is an important note highlighted with the same minimalist border as the table of contents. It can contain **Markdown** and [links](https://gohugo.io/).

{{< /highlight >}}
