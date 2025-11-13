# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## CLIENT:
```python
import socket
s=socket.socket()
s.bind(('localhost', 8001))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
## SERVER:
```python
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())
```
## OUTPUT:

<img width="788" height="335" alt="client" src="https://github.com/user-attachments/assets/cfa436b5-88c8-49e9-aa26-2d6ed9609084" />

<img width="1428" height="408" alt="server" src="https://github.com/user-attachments/assets/0b32a9b6-6f68-4520-8d4e-12cfda6f8dbe" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
