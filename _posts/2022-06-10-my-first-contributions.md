---
title: "My First Contributions"
categories:
  - Open Source Contribution
category: oss
---

# Background
I came across my first opportunity when I was working with scipy and wanted to implement a data transformation that utilized z-scoring. I originally designed the function to be a composition of methods from scipy, and so I naturally went to utilize that zscore function, but had a requirement to skip missing values. This wasn't an option at the time, though a simple solution was to write a zscore function out of two pandas methods.

```
import pandas as pd

def zscore(series):
  return (series - series.mean()) / series.stdev()
```

The pandas mean and standard deviation methods skip missing values by default, but also accept `skip_na` as a parameter. I did this to finish my ticket for the day, but it seemed wasteful to import pandas just for that. I also knew the other scipy methods had the capability to change how they handle missing values, so I thought it was natural to have it here. I had only been writing code professionally for about a year and a half and I was just becoming confident enough to not solely rely on someone telling me how to solve a problem on stackoverflow; I was starting to look at source code myself if I couldn't google for the answer in a reasonable amount of time.

That night I went home and read through the scipy documentation about how to contribute. It was a small change, but it felt cool to organically find something to improve and submit that to the community.

# The first PR

https://github.com/scipy/scipy/pull/10843


After having my first experience, when I came across a similar issue a few months later, I decided to make a similar change. This time it was for the windsorize function.

# My second contribution
https://github.com/scipy/scipy/pull/11619

I mainly focused here on my experience of making a first contribution becuase of how light the actual problem is on details. Recalling this experience has reminded me of how much I enjoyed it and that I want to make a habit of contributing to open source going forward.
