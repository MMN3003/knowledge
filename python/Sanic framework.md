1. create project with virtual `env`. (use [[create project]])
2. install `sanic` package with pip:
```
pip install sanic
```
3. create a file in project root `start.py` with this content:
```
from sanic import Sanic
from sanic.response import text

app = Sanic("MyHelloWorldApp")

@app.get("/")
async def hello_world(request):
    return text("Hello, world.")
```
4. then serve the file by calling it's name after `sanic` command:
```
sanic start
```
