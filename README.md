Part 3: Docker Volumes
\-\-\-\-\-\-\-\-\-\-\-\-\-\-NGINX\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\
Docker volume created by following command
C:\\Users\\HP\\Desktop\\DockerLearning\>docker volume create my_volume
my_volume

C:\\Users\\HP\\Desktop\\DockerLearning\>docker volume ls DRIVER VOLUME
NAME local my_volume

Created container mounted by my_volume

C:\\Users\\HP\\Desktop\\DockerLearning\>docker run -d -p 8080:80 -v
my_volume:/usr/share/nginx/html nginx
7279cd84e14342d6644e94cf256040b22ff59400b0a47cdcc56fee4306aeb881

C:\\Users\\HP\\Desktop\\DockerLearning\>docker ps -a CONTAINER ID IMAGE
COMMAND CREATED STATUS PORTS NAMES 7279cd84e143 nginx
\"/docker-entrypoint....\" 4 seconds ago Up 4 seconds
0.0.0.0:8080-\>80/tcp cool_wilson 61bc8c3b17da 9438dea833aa \"bin/bash\"
4 hours ago Up 4 hours gallant_black 2f1df6dfc2ff 7da20d9f204c \"python
run.py\" 22 hours ago Up 3 hours 0.0.0.0:2010-\>2010/tcp
HelloApp-Container

Nginx default page is accesible on host machine http://localhost:8080/

Index.html file created in D:\\Docker_Mount host machine.

Index file copied to the destination.

C:\\Users\\HP\\Desktop\\DockerLearning\>docker cp
D:\\Docker_Mount\\Index.html 7279cd84e143:/usr/share/nginx/html
Successfully copied 2.05kB to 7279cd84e143:/usr/share/nginx/html

docker stopped C:\\Users\\HP\\Desktop\\DockerLearning\>docker stop
7279cd84e143 7279cd84e143

docker removed C:\\Users\\HP\\Desktop\\DockerLearning\>docker rm
7279cd84e143 7279cd84e143

\-\-\-\-\-\-\-\-\-\-\HTTPD-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\
Created container mounted by my_volume

C:\\Users\\HP\\Desktop\\DockerLearning\>docker run -d -p 8081:80 -v
my_volume:/usr/local/apache2/htdocs httpd
a0831e7d08b98b00995f4509dfc4af477a7b31641e7d4cccc9e3addc861263d9

default HTTPD is accessible

Created About.html in D:\\Docker_Mount host machine.

C:\\Users\\HP\\Desktop\\DockerLearning\>docker cp
D:\\Docker_Mount\\About.html a0831e7d08b9:/usr/local/apache2/htdocs
Successfully copied 2.05kB to a0831e7d08b9:/usr/local/apache2/htdocs

docker stopped C:\\Users\\HP\\Desktop\\DockerLearning\>docker stop
a0831e7d08b9 a0831e7d08b9

docker removed C:\\Users\\HP\\Desktop\\DockerLearning\>docker remove
a0831e7d08b9 a0831e7d08b9

Index and About file are in my_volume.

Removed created my_volume by following command.
C:\\Users\\HP\\Desktop\\DockerLearning\>docker volume rm my_volume
my_volume
