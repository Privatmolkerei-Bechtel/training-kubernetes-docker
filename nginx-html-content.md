# Example nginx with content

```
# das gleich wie cd ~
# Heimatverzeichnis des Benutzers root 
cd
mkdir nginx-test
cd nginx-test
mkdir html
cd html/
# vi index.html
Text, den du rein haben möchtest 

cd ..
vi Dockerfile 

FROM nginx:latest
COPY html /usr/share/nginx/html

# nameskürzel z.B. jm1 
docker build -t dockertrainereu/jm1-hello-web . 
docker images
# eventually you are not logged in 
docker login 
docker push dockertrainereu/jm1-hello-web 
#aus spass geloescht
docker rmi dockertrainereu/jm1-hello-web
# und direkt aus der Registry wieder runterladen 
docker run --name hello-web -p 8888:80 -d dockertrainereu/jm1-hello-web

# laufenden Container anzeigen lassen
docker container ls 
# oder alt: deprecated 
docker ps 

curl http://localhost:8080 



# 
docker rm -f hello-web 

```
