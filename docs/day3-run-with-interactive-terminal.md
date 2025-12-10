# Day 3 Interactive Terminal

  

---

  

## What I did
- Running a docker app written in python using interactive terminals

## What I learnt:
- making a docker container for a python file requiring input
- concept of integrating terminals while running file
- concept of ngnix and kubernetes

to run the file write
`docker run -it project2`

 **meaning of -it**
	-i : interactive
	-t : terminal

## Next Steps
- sharing information between 2 containers

---






## Ngnix
Nginx (pronounced "engine-x") is a high-performance, open-source software that acts as a web server, reverse proxy, load balancer, HTTP cache, and mail proxy, known for its efficiency in handling many concurrent connections, making it popular for serving static content, directing traffic, and scaling web applications.

functions:
- web server -> serving static content (html, css, js) quickly
- load balancing -> distributing traffic across multiple backend servers
- reverse proxy -> directing multiple requests accross servers, sits in front 
- http cache -> download commonly visited pages into a cache for quick access
