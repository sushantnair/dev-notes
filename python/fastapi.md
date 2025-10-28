# 1. FastAPI Basic Code
```python
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI() 
app.add_middleware( 
CORSMiddleware, 
allow_origins=["http://localhost:5173", "http://localhost:5174"],
allow_credentials=True, 
allow_methods=['*'], 
allow_headers=['*']
)

@app.<method; get/post/put/patch/delete>(endpoint/)
def endpoint(...):
```

# 2. Run command
```bash
uvicorn app:app –reload
```
