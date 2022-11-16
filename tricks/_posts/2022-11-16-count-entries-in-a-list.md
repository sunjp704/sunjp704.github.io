---
layout: post
title: "hanzi to pinyin"
tags: python
---

## Use collections.Counter

```python
from collections import Counter

list_a=['apple','apple','apple','banana','banana','orange','orange','orange','orange']
print(Counter(list_a))

----------------------------------
>>> Counter({2: 3, 8: 3, 1: 2, 9: 2, 5: 1, 10: 1})
```