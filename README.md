# Simple REST Server
Simple Python REST Server with POST and GET support

## REQUIREMENTS
- Flask
- JSON

## RUNNING
> python simple_rest_server.py
```
Starting REST service at: 127.0.0.1:3000 ...
 * Running on http://127.0.0.1:3000/ (Press CTRL+C to quit)\
 ```
 
 
## Adding Record
 > curl -d @record.json -H "Content-Type: application/json" http://127.0.0.1:3000/post
 ```
"{u'node': u'local-docker-node', u'resource': u'local-docker/001', u'description': u'Testing', u'source': u'localhost', u'type': u'CentOS', u'severity': u'1'}"
```
### Listing
> curl -v http://localhost:3000/list/all
```
*   Trying ::1...
* connect to ::1 port 3000 failed: Connection refused
*   Trying 127.0.0.1...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> GET /list/all HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.45.0
> Accept: */*
>
* HTTP 1.0, assume close after body
< HTTP/1.0 200 OK
< Content-Type: application/json
< Content-Length: 90
< Server: Werkzeug/0.14.1 Python/2.7.16
< Date: Fri, 04 Oct 2019 18:43:38 GMT
<
[{"node": "test", "type": "test", "resource": "test", "severity": "2", "source": "test"}, {"node": "local-docker-node", "resource": "local-docker-001", "description": "Testing", "source": "localhost", "type": "CentOS", "severity": "1"}]
* Closing connection 0
```
### Listing one entry
> curl -v http://localhost:3000/list/local-docker-001
```
*   Trying ::1...
* connect to ::1 port 3000 failed: Connection refused
*   Trying 127.0.0.1...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> GET /list/local-docker-001 HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.45.0
> Accept: */*
>
* HTTP 1.0, assume close after body
< HTTP/1.0 200 OK
< Content-Type: application/json
< Content-Length: 146
< Server: Werkzeug/0.14.1 Python/2.7.16
< Date: Fri, 04 Oct 2019 18:55:32 GMT
<
{"node": "local-docker-node", "resource": "local-docker-001", "description": "Testing", "source": "localhost", "type": "CentOS", "severity": "1"}
* Closing connection 0
rnatara:~/Solace/Monitor/Plugins/plugins-1.1.1/ServiceNow/test
```
