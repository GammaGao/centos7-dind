# centos7 docker-in-docker
Docker in Docker(dind) image based centos7, could be used by jenkins
- base image: centos7 
- docker18.03.0-ce
- builtin user:jenkinsbuild, Password: jenkinsbuild, build work directory: /home/jenkinsbuild/ci-jenkins
- ssh login

# dind build and run

## build dind image
./build-centos7-dind

## run
docker run -d -p 22 -v /var/run/docker.sock:/var/run/docker.sock centos7-dind  

## copy code to dind
scp -P \<port\> -r \<buildsourcecode\> jenkinsbuild@localhost:/home/jenkinsbuild/ci-jenkins/  

## ssh login dind
ssh -p \<port\> jenkinsbuild@localhost  


# pull from docker hub
docker pull gammagao/centos7-dind  
