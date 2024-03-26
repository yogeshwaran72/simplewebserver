# EX01 Developing a Simple Webserver
## Date:21:2:24

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="pink">
<table border="9" cellspacing="10" cellpadding="10" height="150" width="300" align="center">
<caption> <h3>Top Five Revenue Generating Sotware Companies </h3></caption>
<tr>
<th>Company</th>
<th>Sales(USD)</th>
<th>Nationality</th>
</tr>
<tr>
<th>Microsoft</th>
<th>57.9</th>
<th>USA</th>
</tr>
<tr>
<th>Oracle</th>
<th>21.0</th>
<th>USA</th>
</tr>
<tr>
<th>SAP</th>
<th>16.1</th>
<th>Germany</th>
</tr>
<tr>
<th>Computer Associates</th>
<th>4.2</th>
<th>USA</th>
</tr>
<tr>
<th>Electronic Arts</th>
<th>3.2</th>
<th>USA</th>
</tr>
</table>
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

## OUTPUT:
![image](https://github.com/selvasachein/simplewebserver/assets/153492924/1abfba69-98a3-420b-8205-069e96d5c6fc)
![image](https://github.com/selvasachein/simplewebserver/assets/153492924/1bf4e83f-20ae-4502-9d22-bd24f3596fa3)



## RESULT:
The program for implementing simple webserver is executed successfully.
