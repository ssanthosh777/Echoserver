# Echoserver
Echo server and client using python socket
```
NAME: SANTHOSH S
REG.NO: 212224100052
```
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
## CLIENT
```python
import socket
HOST = "127.0.0.1" 
PORT = 65432  
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"SANTHOSH S, 212224100052")
    data = s.recv(1024)
print(f"Received {data!r}")
```
## SERVER
```python
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
## CLIENT
<img width="1089" height="320" alt="Screenshot 2026-01-30 090114" src="https://github.com/user-attachments/assets/60601787-68e7-4620-b285-1410510daec4" />

## SERVER
<img width="1113" height="309" alt="Screenshot 2026-01-30 090351" src="https://github.com/user-attachments/assets/85ed6459-1199-48c0-afa0-60869a6ef9d5" />


## RESULT:
The program is executed succesfully
