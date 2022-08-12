---
layout: post
title: "pyart's usage notes"
tag: pyart
---

## What is pyart?

Pyart is a python module to read and process weather radar data. Visit [Github homepage](https://github.com/ARM-DOE/pyart)
> The Python ARM Radar Toolkit, Py-ART, is an open source Python module containing a growing collection of weather radar algorithms and utilities build on top of the Scientific Python stack and distributed under the 3-Clause BSD license. Py-ART is used by the Atmospheric Radiation Measurement (ARM) User Facility for working with data from a number of precipitation and cloud radars, but has been designed so that it can be used by others in the radar and atmospheric communities to examine, processes, and analyze data from many types of weather radars.

Install it with conda:

```bash
conda create -n pyart_env -c conda-forge python=3.9 arm_pyart
```

Find examples at [Radar Cookbook](https://cookbooks.projectpythia.org/radar-cookbook/README.html) and [Example Gallery](https://arm-doe.github.io/pyart/examples/index.html)

## Plot refractivity index from CINRAD bin files

Pyart didn't implement CINRAD data format, so we need a decoder for CINRAD bin files. Here are some related works:
> [PyCINRAD](https://github.com/CyanideCN/PyCINRAD)  
> [PyRadar](https://github.com/uniquezhiyuan/PyRadar)  
> [CINRAD数据处理](https://www.jianshu.com/p/ea4baf0cb39b)

According to 薛志远 ([uniquezhiyuan](https://github.com/uniquezhiyuan)), data format of CINRAD bin file is shown below:

|byte|double-byte|data size|remarks|
|:-:|:-:|:-:|:-:|
