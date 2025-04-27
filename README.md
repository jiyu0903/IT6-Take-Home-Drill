1. Extract the server from the file posted. I chose the 86.exe server.
2. Tested the server and observed it's behavior.
3. I noticed that I needed to find the ip address and the port to access the web page. The IP is already given because every computer reserves 127.0.0.1 internally. In finding the port, I went to the Task Manager in my laptop. Find the details tab and and search for the PID of the server in the PID column. After finding it out, i opened cmd and ran this command "netstat -ano | findstr (PID)".
4. After finding the port, I entered it in the web browser and accessed the web page.
5. Next is to find what is needed to send to the server, I captured packets in wireshark while the web page is running.
6. After getting what I needed, next is making a code in python. Import the socket and time module. Created a loop to try all possible 3-digit PINs from 000 to 999. Created a socket. Made a connection to the server. Crafted and sent a proper HTTP POST (the one I captured in wireshark) request containing the current PIN. Received and analyze the response. And encountered errors and tried to fix them properly.
7. I encountered a problem with the output, because the server says to slow down. So I lowered the rest time/delay time to 1 second.
8. By doing so, i was able to find the right pin to the web page, which is 981.
