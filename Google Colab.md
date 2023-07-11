## default

```python
# misc
import sys
import os
# plot
import matplotlib.pyplot as plt
# datascience libs
import numpy as np
import pandas as pd

try: # python
    path_ = os.path.join(os.path.dirname(os.path.abspath(__file__)), "..")
except NameError: # jupyter notebook
    path_ = os.path.dirname(os.getcwd())

dataset_dir = os.path.join(path_, "datasets")
model_dir = os.path.join(path_, "models")
```

## Colab specific
```python
from google.colab import drive
drive.mount('/content/drive')

path_ = "/content/drive/MyDrive/"
dataset_dir = os.path.join(path_, "datasets")
model_dir = os.path.join(path_, "models")
dataset_dir_url = ""
```
