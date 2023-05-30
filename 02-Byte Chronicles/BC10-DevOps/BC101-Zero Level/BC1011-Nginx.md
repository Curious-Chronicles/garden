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
5. [NGINX Linux Server | Common Configurations](https://www.youtube.com/watch?v=MP3Wm9dtHSQ)
6. [Run a Golang, Nginx, and React App in Docker](https://dev.to/shaggyrec/run-a-golang-nginx-and-react-app-in-docker-59kn)
7. [404 Not Found with Docker, React Router and Nginx | by Patrick O'Neill | Medium](https://patrickjamesoneill.medium.com/404-not-found-with-docker-react-router-and-nginx-21fdce02c5)
8. 

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


### Nginx Terminology

1. Directives are those with key value pair or in programming term: variable. 
2. Context: is the wrapper that encapsulates them with, or in programming term: function.

# Coding the Nginx Conf

1. Create a simple HTML, CSS and JS files.
2. Implement the below code.
```nginx
 http{
        server {
                listen 80;
              root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
       }
}

 events{}
```

3. The above code will server the html in that directory to the localhost:80. However, although the CSS and JS will load, it will not work correct. 
4. Setting the MIME Type. Use the following code.

```nginx
http{
        types{
                text/css        css;
                text/html       html;
                text/js         js;
        }
        server {
                listen 80;
                root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
        }
}

events{}
```

```ad-tip

Nginx has many of the default mime.types for easiness. That are in mime.types files witin the nginx folder. 

Below is an simple example of using nginx default mime types.

```nginx
http{
        include mime.types;

        server {
                listen 80;
                root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
        }
}

events{}
```

5. To open up a location within the folder, we can use the `location context` to define another `/{url}` 

```nginx
http{
        include mime.types;

        server {
                listen 80;
                root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;

                location /fruits{
                        root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
                }
        }
}

events{}
```

```ad-warning
Mind you in the above code we didn't define where this /fruits index.html is located at. However, it serves it autoamtically by appending the /fruits at the end of root dir. 

```nginx
location /fruits{
    root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
}

```

```ad-tip
However, if you don't want to auto append the location {url} at the end of the root then do not use "root" and instead use alias

```nginx
location /carbs{
   alias /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites/fruits;
}
```


```ad-note

Since by default nginx will search index.html, if that is not present, you need to make sure there are other options accounted for. to do this, use `try files` directives. 

```nginx

 location /veg{
	root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
	try_files /veg/veg.html /index.html =404;
}

```


```ad-note
If you want to put regular express in the location you can do so by 

```nginx
location ~* /count/[0-9]{
	root /home/sarweshmaharjan/code/work/sarweshmaharjan/nginx-sites;
	try_files /index.html =404;
}
```


# Redirect and Rewrite

To do a redirect to other location, you can do the following 

```nginx
 location /carbs{
	return 307 /fruits;
}
```

What it is doing is, redirecting the /carbs to /fruits, 307 is just the HTTP for redirect.

```ad-warning
However, by doing this you will run into the issue of chaning the {url} which was /carbs to /fruits. If you want to let {url} remain the same then you need to use rewrite.
```

To rewrite you can use the following. In rewrite we do not need location. We just need to map the new `{new_url}` to `{old_url}`

```nginx
# Whatever is written on (\w+) will be send to $1 
rewrite ^/number/(\w+) /count/$1
```


# Simple Load Balancer

One of the simplest load balancer algorithm it uses is, round-robin algorithm. An example of this is. 

```nginx

http{
	upstream backendserver {
		server 127.0.0.1:1111;
		server 127.0.0.1:2222;
		server 127.0.0.1:3333;
		server 127.0.0.1:4444;
	}
	server {
		listen 80; 
		location / {
			proxy_pass http://backendserver/;
		}
	}
}
```


# Lesson learned

1. By default nginx have there won't conf files that might conflict with yours. One of the simplest of example is when we hit any URL except `/` it will show 404 Not found, even though it was properly conf in yours. 
```nginx
include /etc/nginx/conf.d/*.conf;
# comment this line to 
# include /etc/nginx/conf.d/*.conf;
```

2. `proxy_pass` is the directory that cannot be used within the `nginx.conf` file. It needs to be in either the `conf.d/default.conf` or any other .conf file.  A general rule of thumb is, using "nginx" folder containing the `conf.d/default.conf` and `nginx.conf` file and replacing them with the current `nginx.conf` and `default.conf` file present within the container.

```nginx
# to replace the deafult nginx.conf file.
user nginx;

worker_processes auto;

  

error_log /var/log/nginx/error.log notice;

pid /var/run/nginx.pid;

  
  

events {

worker_connections 1024;

}

  
  

http {

include /etc/nginx/mime.types;

default_type application/octet-stream;

  

log_format main '$remote_addr - $remote_user [$time_local] "$request" '

'$status $body_bytes_sent "$http_referer" '

'"$http_user_agent" "$http_x_forwarded_for"';

  

access_log /var/log/nginx/access.log main;

  

sendfile on;

#tcp_nopush on;

  

keepalive_timeout 65;

  

#gzip on;

  

# include /etc/nginx/conf.d/*.conf;

  

server {

listen 80;

server_name ec2-3-130-128-23.us-east-2.compute.amazonaws.com;

resolver 8.8.8.8 valid=10s;

  

types {

application/typescript ts;

application/javascript js;

text/html html;

text/css css;

text/scss scss;

image/svg+xml svg;

image/jpeg jpeg jpg;

image/png png;

}

  

location / {

root /usr/share/nginx/html;

index index.html index.htm;

proxy_set_header Host $host;

proxy_set_header X-Real-IP $remote_addr;

proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

try_files $uri $uri/ /index.html?/$request_uri;

}

}

}
```

```nginx
# to replace the deafult default.conf file. 
server {

listen 8080;

server_name ec2-3-130-128-23.us-east-2.compute.amazonaws.com;

resolver 8.8.8.8 valid=10s;

location / {

proxy_pass: http://0.0.0.0:8080/;

proxy_set_header Host $host;

proxy_set_header X-Real-IP $remote_addr;

proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

}

}
```

3. Docker of the react and golang. Below code are for reference purpose. 

```Dockerfile
# client side docker file with nginx and react container
# Use the official Node.js 16 image as the parent image

FROM node:16 AS build

  

# Set the working directory

WORKDIR /usr/src/app

  

# Copy the package files to the working directory

COPY package*.json ./

  

# Install dependencies

RUN yarn install

  

# Copy the rest of the application code to the working directory

COPY . .

  

# Build the application with Vite

RUN yarn build

  

# Use the official Nginx image as the parent image

FROM nginx:latest

  

# Copy the built files from the previous stage to the Nginx web server directory

COPY --from=build /usr/src/app/dist /usr/share/nginx/html

  

# Copy the Nginx configuration file to the container

COPY nginx/nginx.conf /etc/nginx/nginx.conf

COPY nginx/default.conf /etc/nginx/conf.d/default.conf

  

# Expose port 80

EXPOSE 80

  

# Start Nginx in the foreground

CMD ["nginx", "-g", "daemon off;"]
```

```Dockerfile
# server side docker file with golang 
# Dockerfile for the Server Side of Leapflow

FROM golang:1.20-alpine3.17

  

RUN addgroup -S leapflow && adduser -S leapflow -G leapflow

  

WORKDIR /server

  

COPY . .

  

RUN go build -o server ./cmd/main.go

  

RUN chown -R leapflow:leapflow /server

  

EXPOSE 8080

  

CMD ["./server"]
```

```yml
# docker composer setup for all including the postgres server
version: '3'

  

services:

db:

image: postgres:13-alpine

volumes:

- postgres-data:/var/lib/postgresql/data

env_file:

- db.env

ports:

- "5432:5432"

networks:

- leapflow-network

container_name: leapflow-db

  

server:

build:

context: ./server

dockerfile: Dockerfile

env_file:

- ./server/server.env

restart: always

volumes:

- ./server:/app

ports:

- "8080:8080"

depends_on:

- db

networks:

- leapflow-network

container_name: leapflow-server

  

app:

build:

context: ./app

dockerfile: Dockerfile

env_file:

- ./app/app.env

volumes:

- ./app:/app

ports:

- "80:80"

- "443:443"

depends_on:

- server

restart: always

networks:

- leapflow-network

container_name: leapflow-app

  

volumes:

postgres-data:

networks:

leapflow-network:
```