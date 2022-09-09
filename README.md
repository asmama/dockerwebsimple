# dockerwebsimple
docker http2


# code structure

- Dockerfile :
  - get base image of apache webserver, tag 2.4. 
  - copy index.html to replace the existing index.html
  - by default it will expose port 80
  - you can change the port using EXPOSE inside Dockerfile

``
`FROM httpd:2.4
 
COPY ./index.html/ /usr/local/apache2/htdocs/
```
# To build

- go into the directory

root@ip-172-31-6-55:~/gg/dockerwebsimple# docker build -t asmama/web:1.0.0 .
Sending build context to Docker daemon  68.61kB
Step 1/2 : FROM httpd:2.4
 ---> a981c8992512
Step 2/2 : COPY ./index.html/ /usr/local/apache2/htdocs/
 ---> Using cache
 ---> 95f34a117245
Successfully built 95f34a117245
Successfully tagged asmama/web:1.0.0

- check the image

root@ip-172-31-6-55:~/gg/dockerwebsimple# docker image ls | grep web
asmama/web   1.0.0     95f34a117245   2 hours ago   145MB
asmama/web   latest    95f34a117245   2 hours ago   145MB
