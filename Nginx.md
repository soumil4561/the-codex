Open source software for: 
- web serving
- reverse proxy
- caching
- load balancing
- media streaming etc.

# Introduction

![[Pasted image 20240717230855.png]]

The nginx serves content by default from : /usr/share/nginx/html/

We can create a live mount point using docker compose/ dockerfile to use nginx to host our web app and work on it side by side. 
```Docker-compose
	services:
		nginx:
			build:
				context .
			ports:
				- 8000:80
			volumes:
				- ./html:/usr/share/nginx/html
```

Also we can create image using dockerfile and then use that on servers
```Dockerfile
FROM nginx:latest
COPY ./html/index.html /usr/share/nginx/html/index.html
```

# Architecture
![[Pasted image 20240717235434.png]]

So here there are 4 worker process controlled by a master process. Worker process can be configured, though the defualt in nginx is 1 worker /cpu. So for 16 threads = 16 worker process.
![[Pasted image 20240718001243.png]]
**Master Process** controls the startup, reload configuration of the service. 
**Worker Process** actually do the work. They listen on the incoming sockets for request and work on them as per need.

*Configuration* for the same can be done using `nginx.conf` in the `/etc/nginx/nginx.conf`

After changing the value, signal the nginx for change using `nginx -s reload`

![[Pasted image 20240718002143.png]]
As multiple services go up, they are managed via the load balancer
