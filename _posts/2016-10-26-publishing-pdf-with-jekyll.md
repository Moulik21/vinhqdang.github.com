---
layout: post
title: "Publishing PDF with Jekyll"
description: ""
layout: pdf
category: tutorial
tags: [trick,usage,jekyll]
---
{% include JB/setup %}

I followed [the tutorial](http://jamesonzimmer.com/simple-pdf-embed-for-jekyll/) but instead of using *height="100%"*, I used *height="50em"*.

## Using iframe

<iframe src="/pdf/brain_in_a_vat.pdf" width="100%" height="800em">
This browser does not support PDFs. Please download the PDF to view it: <a href="/pdf/brain_in_a_vat.pdf">Download PDF</a>
</iframe>

## Using embed

<embed src="/pdf/brain_in_a_vat.pdf" type="application/pdf" width="100%" height="800px">