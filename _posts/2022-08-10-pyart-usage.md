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

According to 薛志远 ([uniquezhiyuan](https://github.com/uniquezhiyuan)), SA/SB radar bin file is composed of several 2732-bytes-sized data units and the format of each unit can be written in the form of numpy.dtype as:

```python
header = [
    ('reserved1', '14B'),
    ('radar', 'i2'),
    ('reserved2', '12B')
]

description = [
    ('time', 'u4'),
    ('date', 'u2'),
    ('unambiguous_range', 'u2'),
    ('azimuth','u2'),
    ('radial_index','u2'),
    ('radial_status','u2'),
    ('elevation','u2'),
    ('num_elevation','u2'),
    ('start_refractivity_range_bin','u2'),
    ('start_doppler_range_bin','u2'),
    ('step_refractivity_range_bin','u2'),
    ('step_doppler_range_bin','u2'),
    ('num_refractivity_range_bin','u2'),
    ('num_doppler_range_bin','u2'),
    ('sector','u2'),
    ('adjustment','u4'),
    ('refractivity_pointer','u2'),
    ('doppler_pointer','u2'),
    ('spectrum_width_pointer','u2'),
    ('resolution_doppler','u2'),
    ('volume_cover_pattern','u2'),
    ('reserved3','4B'),
    ('bk_refractivity_pointer','u2'),
    ('bk_doppler_pointer','u2'),
    ('bk_spectrum_width_pointer','u2'),
    ('nyquist_velocity','u2')
]

data = [
    ('reserved1','19B'),
    ('refractivity','460u1'),
    ('doppler_velocity','920u1'),
    ('spectrum_width','920u1'),
    ('reserved2','14B')
]
```
