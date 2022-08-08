---
layout: post
title: "Jekyll Tips"
tags: Jekyll MathJax
---

# inline math
To enable `$...$` as the inline math delimeter, add this to head.html:
```html
  <script>
    MathJax = {
      tex: {
        inlineMath: [['$', '$'], ['\\(', '\\)']]
      }
    };
  </script>
```