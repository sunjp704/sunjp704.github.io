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
    pin[0].capitalize()
    for i in range(len(pin)):
        cap_pin=cap_pin+pin[i]
    return cap_pin

--------------------------------
>>> print(han2pin('哈哈'))
Haha

```
