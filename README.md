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
## OUTPUT
<img width="828" height="327" alt="Screenshot 2026-05-11 104026" src="https://github.com/user-attachments/assets/1c237287-4ffb-40c9-8758-714247da26ee" />
<img width="1482" height="273" alt="Screenshot 2026-05-11 104005" src="https://github.com/user-attachments/assets/c7dd4134-02fa-4357-9ab6-0c0def6bec4b" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
