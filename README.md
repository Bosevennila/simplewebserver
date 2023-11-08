# EX01 Developing a Simple Webserver
## Date: 07.10.23

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
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<table border="2">
<caption> Top Five Revenue Generating Software Companies</caption>
<tr>
<th>S.No</th>
<th>Company</th>
<th>Revenue</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft</td>
<td>65 Billion</td>
</tr>
<tr>
<td>2</td>
<td>Oracle</td>
<td>29.6 Billion</td>
</tr>
<tr>
<td>3</td>
<td>IBM</td>
<td>29.1 Billion</td>
</tr>
<tr>
<td>4</td>
<td>SAP</td>
<td>6.4 Billion</td>
</tr>
<tr>
<td>5</td>
<td>Symantec</td>
<td>5.6 Billion</td>
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
```

## OUTPUT:
![Alt text](<Screenshot 2023-11-08 105757.png>)
![Alt text](<Screenshot 2023-11-08 105842.png>)
![Screenshot 2023-11-08 105757](https://github.com/Bosevennila/simplewebserver/assets/144870486/9ebadf6b-df63-47ce-be89-a8da3d86b343)
![Screenshot 2023-11-08 105842](https://github.com/Bosevennila/simplewebserver/assets/144870486/8b991e0e-e704-402d-ac39-ad2549069cbb)



## RESULT:
The program for implementing simple webserver is executed successfully.
