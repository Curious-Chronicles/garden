---
index: BC1011
tags: zero-knowledge, devops, nginx
status: Started
created: 2023-05-06 14:45
updated:  <%+ tp.file.last_modified_date("dddd Do MMMM YYYY") %>
---
Related: {{related}}
URL: 
1. [NGINX Explained in 100 Seconds](https://www.youtube.com/watch?v=JKxlsvZXG7c)
2. [Nginx in 120 Seconds (for beginners)](https://www.youtube.com/watch?v=oZXWVom0n8o)
3. [Proxy vs Reverse Proxy (Real-world Examples)](https://www.youtube.com/watch?v=4NB0NDtOwIQ)
4. [The NGINX Crash Course](https://www.youtube.com/watch?v=7VAI73roXaY)
5. 

---

# What is Nginx?

Nginx is a web server that act as a reverse proxy that stands between the server and client. It gets all the request from the client and balances the load sending to multiple server thereafter. We can also add SSL and firewall in one location instead of adding to multiple server. 



# Step Nginx in your system

For ubuntu distro: 

1. Install nginx in your system
```shell
sudo apt-get update
sudo apt-get install nginx
```

2. Start and see the nginx service status. 
```shell
sudo systemctl start nginx.service
sudo systemctl status nginx.service
```

# Configuring Nginx 

Nginx is located at `sudo vim /etc/nginx/nginx.conf` . 

A simple nginx configuration is divided into three section:
1. Worker's count
2. Definition of backends
3. Create listen service[s]

```nginx
events {
	worker_connections 4096; ## Default: 1024
}

http {
	upstream big_server_com {
		server 127.0.0.1:8080 weight=5;
		server 127.0.0.1:8081 weight=5;
	}
	server {
		listen 80;
		server_name: big.server.com;
		location / {
			proxy_pass http://big_server_com;
		}
	}
}
```

# Getting Started with Nginx

To get nginx to start, all you need to do is type "nginx" in terminal and open browser and type, localhost:80

```shell
# start
nginx

# stop
nginx -s quit
nginx -s stop
```

