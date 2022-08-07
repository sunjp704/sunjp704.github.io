---
layout: post
title: "Jerkyll tips"
date: 2022-08-07 13:14:00 +8000
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