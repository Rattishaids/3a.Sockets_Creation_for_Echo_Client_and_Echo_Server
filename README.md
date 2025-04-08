3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
AIM
To write a python program for creating Echo Client and Echo Server using TCP Sockets Links.

ALGORITHM:
Import the necessary modules in python
Create a socket connection to using the socket module.
Send message to the client and receive the message from the client using the Socket module in server .
Send and receive the message using the send function in socket.
PROGRAM
server:
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server_socket:
    server_socket.bind((HOST, PORT))
    server_socket.listen()

    print(f"Server is listening on {HOST}:{PORT}")
    while True:
        conn, addr = server_socket.accept()
        with conn:
            print(f"Connected by {addr}")
            while True:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
                print(f"Echoed: {data.decode('utf-8')}")
client:
import socket

HOST = '127.0.0.1'  
PORT = 65432  

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
    client_socket.connect((HOST, PORT))

    message = 'Hello, Server!'
    client_socket.sendall(message.encode('utf-8'))

    data = client_socket.recv(1024)
    print(f"Received echo: {data.decode('utf-8')}")
OUPUT

![image](https://github.com/user-attachments/assets/3e95fdce-cab8-41b3-90a4-d1c3aec9df44)

![image](https://github.com/user-attachments/assets/441ddd48-ddcd-4088-861d-024236e71e0f)



RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
