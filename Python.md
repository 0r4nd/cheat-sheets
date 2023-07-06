

## Timer decorator ⏲️ (time a function)
```python
from time import time
from sys import argv

def _time(f):
    def wrapper(*args):
        start = time()
        r = f(*args)
        end = time()
        print("%s(): timed %fs" % (f.__name__, end-start))
        return r
    return wrapper

## Usage
@_time
def time_me(dir_path:str):
    for i in range(10000):
        pass
```
