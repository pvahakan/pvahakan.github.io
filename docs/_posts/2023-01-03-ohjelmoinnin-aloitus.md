---
layout: post
title: "Ohjelmoinnin aloitus"
date: 2023-01-03
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Ohjelmoinnin aloitus

Tässä teille yksi koodinpätkä:

```python
for i in range(10):
    print(i)
```

Toimiikohan LaTex suoraan? Tässä pitäisi näkyä tuttu lauseke, jolla voi laskea ympyrän pinta-alan, kun säde tiedetään.

$$
A = \pi r^2
$$

Pythonilla vastaava voitaisiin laskea ja tulostaa näkyviin seuraavasti:

```python
import math

r = 10
ala = math.pi * r**2
print(ala)
```