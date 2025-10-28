# 1. Go up one level from current dir
## METHOD 1: Using pathlib (most pythonic)
```python
from pathlib import Path 
# Go up 1 level 
Path(__file__).parent 
# Go up 2 levels 
Path(__file__).parent.parent
```
## METHOD 2: Using os
```python
# Go up 2 levels 
os.path.join(__file__, '..', '..') 
# Go up n levels 
os.path.join(__file__, *(['..'] * n)) 
# But you need to normalize it 
os.path.normpath(os.path.join(__file__, '..', '..'))
```

# 2. Mute Warning
```python
import warnings 
from urllib3.exceptions import InsecureRequestWarning

warnings.filterwarnings('ignore', category=InsecureRequestWarning)
```


