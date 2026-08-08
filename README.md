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
## PROGRAM
```
SERVER PROGRAM:

import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()

CLIENT PROGRAM:

import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()

```
<img width="653" height="536" alt="Screenshot 2026-08-08 102004" src="https://github.com/user-attachments/assets/07fcfad4-b2d2-4c4b-a6d1-9a0a02631a39" />
<img width="633" height="447" alt="Screenshot 2026-08-08 102334" src="https://github.com/user-attachments/assets/18732ff5-7914-4666-958c-b43c50a0da43" />

## OUTPUT


















































































































































































































































<img width="1302" height="376" alt="Screenshot 2026-08-08 102351" src="https://github.com/user-attachments/assets/46d39ea3-efe7-4589-bbfa-075f5802623c" />

<img width="1297" height="387" alt="Screenshot 2026-08-08 102325" src="https://github.com/user-attachments/assets/ed92afdc-1249-491f-95bd-9d7c0f37a9d5" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
