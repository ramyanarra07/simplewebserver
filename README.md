# EX01 Developing a Simple Webserver
## Date:27-02-2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Top 5 Software Companies in Revenue</title>
</head>
<body>
<h1 align="center">Top Five Software Companies in Revenue </h1>
<table align="center" width="540" cellspacing="2" cellpoding="4" border="2">
<tr align="center">
        <th bgcolor="aquablue">S.NO</th>
        <th bgcolor="aquablue">NAME OF THE COMPANY</th>
        <th bgcolor="aquablue">REVENUE</th>
        <th bgcolor="aquablue">GROWTH RATE</th>
        </tr>
        <tr align="center">
        <td>1</td>
        <td>Microsoft</td>
        <td>$32.2B</td>
        <td>39%</td>
        </tr>
        <tr align="center">
        <td>2</td>
        <td>Amazon</td>
        <td>$35.03B</td>
        <td>37%</td>
        </tr>
        <tr align="center">
        <td>3</td>
        <td>IBM</td>
        <td>$35.03B</td>
        <td>14%</td>
        </tr>
        <tr align="center">
        <td>4</td>
        <td>Salesforce</td>
        <td>$17.1B</td>
        <td>25%</td>
        <tr align="center">
        <td>5</td>
        <td>Goole</td>
        <td>$8.92B</td>
        <td>53%</td>
        </tr>
        </body>
        </html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:

![alt text](<Screenshot (21).png>)

![alt text](<Screenshot (30).png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
