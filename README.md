# run-fastapi

### 1. Python 설치

먼저, Python이 설치되어 있는지 확인합니다. 설치되어 있지 않다면 [Python 공식 사이트](https://www.python.org/downloads/)에서 최신 버전을 다운로드하여 설치합니다.

### 2. 가상 환경 설정

```bash
# 프로젝트 디렉토리 생성
mkdir fastapi
cd fastapi

# 가상 환경 생성
python -m venv venv

# 가상 환경 활성화 (Windows)
venv\Scripts\activate

# 가상 환경 활성화 (macOS/Linux)
source venv/bin/activate
```

### 3. FastAPI와 Uvicorn 설치

```bash
pip install fastapi uvicorn
```

### 4. FastAPI 애플리케이션 생성

```python
# main.py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

### 5. 애플리케이션 실행

Uvicorn을 사용하여 FastAPI 애플리케이션을 실행합니다.

```bash
uvicorn main:app --reload
```
