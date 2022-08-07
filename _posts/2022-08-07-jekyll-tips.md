---
layout: post
title: "Jekyll tips"
categories: Jekyll MathJax
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