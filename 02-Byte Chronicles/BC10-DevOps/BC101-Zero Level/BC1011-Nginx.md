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
