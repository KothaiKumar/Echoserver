# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
## SERVER
```python
import socket
HOST="127.0.0.1" 
PORT=65432
with socket.socket(socket.AF_INET,socket.SOCK_STREAM) as s:
	s.bind((HOST,PORT))
	s.listen()
	conn,addr = s.accept()
	with conn:
		print(f"Connected by {addr}")
		while True:
			data=conn.recv(1024)
			if not data:
				break
			conn.sendall(data)
```
## CLIENT
```python
import socket
HOST="127.0.0.1"
PORT=65432
with socket.socket(socket.AF_INET,socket.SOCK_STREAM) as s:
	s.connect((HOST,PORT))
	s.sendall(b"Hello,world")
	data=s.recv(1024)
	print(f"Recieved {data!r}")
```

## OUTPUT:
## CLIENT
![image](https://github.com/KothaiKumar/Echoserver/assets/121215739/927535b1-da29-4eff-8471-00132ff3335e)

## SERVER
![image](https://github.com/KothaiKumar/Echoserver/assets/121215739/32e5acf3-7319-4e3a-92e9-cd92735ece6b)

## RESULT:
The program is executed successfully
