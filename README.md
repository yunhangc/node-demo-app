# node demo app

## Docker
```
docker build -t yourlogin/node-demo-app .
docker push yourlogin/node-demo-app
```

## Debian package (\*.deb file)
```
docker build -t builddep -f Dockerfile.builddep .
docker run -it -v $PWD:/root builddep
cd /root
apt-get install -y npm
git-buildpackage  # creates *.deb file in node-demo-app_<version>_<arch>.deb
exit
cp <container_id>:/node-demo-app_<version>_<arch>.deb .
```
