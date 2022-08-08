---
layout: post
title: "Radar Meteorology 2: Radar reflectivity and products"
categories: radar meteorology
---
Notes of [Fabry, F. (2018). *Radar meteorology: principles and practice*. Cambridge University Press.](https://www.cambridge.org/id/academic/subjects/earth-and-environmental-science/atmospheric-science-and-meteorology/radar-meteorology-principles-and-practice?format=AR) Ch. 3

## The radar equation

Most precipitation targets are much smaller than the usual radar wavelength (Rayleigh scatterers). For such targets, we define $Z$ as the radar reflectivity factor per unit volume:

$$
Z=\int _0^{\infty}N(D)D^6\mathrm{d}D
$$

Note that $Z$ is usually expressed in nonstandard units of $\mathrm{mm^6}/\mathrm{m^3}$

A convenient version of radar equation for radars with parabolic antennas is

$$
P_\mathrm{r}=\frac{1.22^2\times 0.55^2\times 10^{-18}\pi^7c}{1024\ln2}\frac{P_\mathrm{t}\tau D_\mathrm{a}^2}{\lambda^4}\frac{T^2(0,r)}{r^2}\Vert K\Vert^2Z
$$

```md
first term: constants
second term: radar parameters
third term: path
the rest: target properties
```

where $P_t$ is the power of the transmit pulse and $\tau$ its duration; $D_\mathrm{a}$ is the diameter of the antenna; $T$ is the transmittance of the atmosphere along the path between the radar at range 0 and the sampling volume at range $r$, and $\Vert K\Vert^2$ is the dielectric constant of the scatterers and is related to the complex index of refraction of the hydrometeor $n(\lambda)$ via

$$
\Vert K\Vert^2=\left\Vert\frac{n^2(\lambda)-1}{n^2(\lambda)+2}\right\Vert^2
$$

## The equivalent reflectivity factor

In most cases, we don't know for certain about the nature of the targets ($\Vert K\Vert^2$?, Rayleigh scattering or not). Because of that, we define the equivalent factor $Z_\mathrm{e}$ such that

$$
P_\mathrm{r}=\frac{1.22^2\times 0.55^2\times 10^{-18}\pi^7c}{1024\ln2}\frac{P_\mathrm{t}\tau D_\mathrm{a}^2}{\lambda^4}\frac{T^2(0,r)}{r^2}\Vert K_\mathrm{w}\Vert^2Z_\mathrm{e}
$$

with $\Vert K_\mathrm{w}\Vert^2$ being the dielectric constant of liquid water(0.93). Normally, it is the $Z_\mathrm{e}$ that is measured by the radar.

For convenience, we generally express reflectivity factors in units of decibels (dB) as

$$
\mathrm{dB}Z=10\log _{10}Z
$$

## Reflectivity factor and rain rate

reflectivity factor:

$$
Z=\int _0^{\infty}N(D)D^6\mathrm{d}D
$$

rainfall rate:

$$
R=\int _0^{\infty}N(D)D^3w_\mathrm{r}(D)\mathrm{d}D
$$

$w_\mathrm{r}(D)$: fall speed of a raindrop of diameter $D$.

There are no mathematical functions linking $Z$ and $R$. On average, however, DSD varies systematically with reflectivity and precipitation intensity. $Z$-$R$ relationships are derived based on that fact:

$$
\begin{aligned}
    & Z=200R^{1.6}\qquad\mathrm{Marshall-Palmer\ 1950s} \\
    & Z=300R^{1.5}\qquad\mathrm{Joss\ and\ Waldvogel\ 1970} \\
    & Z=300R^{1.4}\qquad\mathrm{WSR-88D}
\end{aligned}
$$

$Z$-$R$ relationships power laws of the form $Z=aR^b$ of which the coefficients $a$ and $b$ depend on the dynamics and microphysics processes controlling precipitation formation. Hence, it varies from one region to another.

## Radar products

1. Vertical cross sections
2. Vertically integrated liquid (VIL)
3. ...
