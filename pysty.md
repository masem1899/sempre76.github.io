---
layout: default
title: PySty
---
## PySty - Python Styling Library
### Enrich your Python Component Library with styles injected via decorators.

#### Easy to use:
<pre>```python
from abc import ABC
from pysty import pysty

@pysty({
    'text-color':DefaultTheme['tc_danger']
})
class BaseLabel(ABC) {
    ...
}
```</pre>

#### Features:
- Easy to integrate
- Supports multiple style themes
- No dependencies
- One decorator and some helper functions
