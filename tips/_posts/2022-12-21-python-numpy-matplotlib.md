---
layout: post
title: "python, numpy, matplotlib"
---

## matplotlib animation
To save the animation made by matplotlib.animation as a .mp4 file, you need to first install ffmpeg, and then pointing ffmpeg_path to the ffmpeg executable file.

```python
import matplotlib as mpl 
mpl.rcParams['animation.ffmpeg_path'] = 'your_path/bin//ffmpeg.exe'
```

Next, use matplotlib.animation.Animation.save() method to save your animation.

```python
ani = animation.FuncAnimation(fig, update, interval=10)
writer = animation.FFMpegWriter(fps=60)
ani.save('video.mp4', writer=writer)
```
