# 2a_Stop_and_Wait_Protocol
# Name: Kishor Kumar B
# Reg. No: 212223240072
# Date :
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

# Client:
~~~python
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
~~~

# Server:

~~~python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
~~~
## OUTPUT
![Output](https://github.com/user-attachments/assets/16e16712-9d75-4bee-ab22-fe58047ec49e)
T

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
