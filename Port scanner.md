import socket

print("Welcome to Port Scanner")
print("Podaj IP celu:")
IP = input("IP:")

print("Wybierz scan \n 1. TCP \n 2. UDP")
choice = input("Wybierz:")

if choice == "1":
    for port in range(1, 65536):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) #scan IPv4 + TCP
        wynik = s.connect_ex((IP, port))
        s.close()
        if wynik == 0:
            print("Port", port, "jest otwarty")

elif choice == "2":
    for port in range(1, 65536):
        s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM) #scan IPv4 + UDP
        wynik = s.connect_ex((IP, port))
        s.close()
        if wynik == 0:
            print("Port", port, "jest otwarty")
