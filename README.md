# EX01 Developing a Simple Webserver


## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
Name:Balaji Arambakam
Reg no: 212224230021
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content="""<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table border="1" align="center" cellpadding="10" bgcolor="magenta">
        <tr>
            <caption>
                <h1>
                    List of Protocols in Tcp/Ip Protocol Suite
                </h1>
            </caption>
        </tr>
        <tr>
            <th>S.No</th><th>Name of the layer</th><th>Name of the protocol</th>
        </tr>
        <tr>
            <td>1</td><td>Application layer</td><td>HTTP,FTP,DNS,TELENET</td>
        </tr>
        <tr>
            <td>2</td><td>Transport layer</td><td>Tcp & Udp</td>
        </tr>
        <tr>
            <td>3</td><td>Network layer</td><td>IPV4/IPV6</td>
        </tr>
        <tr>
            <td>4</td><td>Link Layer</td><td>Ethernet</td>
        </tr>
    </table>"
</body>
</html>"""

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

```

## OUTPUT:
<img width="1920" height="1200" alt="Screenshot 2025-09-01 083700" src="https://github.com/user-attachments/assets/39e7a6c0-d9fe-4855-9ec2-b6d142041557" />



## RESULT:
The program for implementing simple webserver is executed successfully.
