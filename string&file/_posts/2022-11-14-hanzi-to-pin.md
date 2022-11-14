---
layout: post
title: "hanzi to pinyin"
tags: string
---
## pypinyin

Use python package [pypinyin](https://pypi.org/project/pypinyin/) to transfer hanzi into pinyin.

```python
from pypinyin import lazy_pinyin

def han2pin(han:str):
    pin=lazy_pinyin(han)
    cap_pin=pin[0].capitalize()
    for i in range(1,len(pin)):
        cap_pin=cap_pin+pin[i]
    return cap_pin

--------------------------------
>>> print(han2pin('汉字'))
Hanzi

```
