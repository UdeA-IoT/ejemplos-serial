# Paso 4 - Creación del API para controlar el arduino

## Prerequisitos



## Software

```python
#Python
from typing import Optional
from enum import Enum
import serial

#Pydantic
from pydantic import BaseModel
from pydantic import Field

#FastAPI
from fastapi import FastAPI
from fastapi import Body, Query, Path

app = FastAPI()
app.serial = None

@app.get("/")
def home():
    return {"App": "Ready"}

@app.get("/connect")
def connect(): 
    print("Iniciando conexión...")
    app.serial = serial.Serial('COM8',115200)
    if app.serial == None:
        return {"Connection": "Fail"}
    else:
        return {"Connection": "Open"}

@app.get("/disconnect")
def disconnect():
    app.serial.close()
    return {"Connection": "Close"}

@app.get("/on")
def led_on():
    app.serial.write('H'.encode())
    return {"led":"on"}

@app.get("/off")
def led_off():
    app.serial.write('L'.encode())
    return {"led":"off"}
```

## Probando la aplicación


