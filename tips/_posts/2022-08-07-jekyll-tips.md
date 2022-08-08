---
layout: post
title: "Jekyll Tips"
tags: Jekyll MathJax
---

## inline math

To enable `$...$` as the inline math delimiter, add this to head.html:

```html
  <script>
    MathJax = {
      tex: {
        inlineMath: [['$', '$'], ['\\(', '\\)']]
      }
    };
  </script>
```
