直接pull已经制作好的镜像，并用启动命令启动

docker pull 13660129620/jenkins:1.609

docker run -d -p 8080:8080 --restart=always --name jenkins -v /usr/bin/docker:/usr/bin/docker  -v /var/run/docker.sock:/var/run/docker.sock -v /var/jenkins_home:/var/jenkins_home -v /usr/lib64/libltdl.so.7:/usr/lib64/libltdl.so.7  -v /root/.ssh/:/root/.ssh  13660129620/jenkins:1.609




git clone git@github.com:hx6007/docker-in-jenkins.git  && cd docker-in-jenkins && ./install.sh

cd  centos7/

docker build -t  csphere/centos:7.1 .


cd ../jdk

docker build -t  csphere/jdk:1.7.0 .

cd ../jenkins/

docker build -t csphere/jenkins:1.609 .

docker run -d -p 8080:8080 --restart=always --name jenkins -v /usr/bin/docker:/usr/bin/docker  -v /var/run/docker.sock:/var/run/docker.sock -v /var/jenkins_home:/var/jenkins_home -v /usr/lib64/libltdl.so.7:/usr/lib64/libltdl.so.7  -v /root/.ssh/:/root/.ssh  csphere/jenkins:1.609
