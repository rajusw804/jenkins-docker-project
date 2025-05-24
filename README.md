Jenkins installation:

Terraform installation:

sudo dnf update

sudo install git maven docker -y
   
sudo  systemctl start docker
     
sudo systemctl enable docker

sudo dnf install java-17-amazon-corretto -y

sudo mount -o remount,size=2G /tmp

sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

sudo dnf install jenkins -y

sudo systemctl enable jenkins

sudo systemctl start jenkins

df -h /tmp

sudo mount -o remount,size=2G /tmp

vi /etc/fstab

tmpfs /tmp tmpfs defaults,size=2G 0 0 # Change 2G to your desired size

   
   13  sudo yum install jenkins
-------------------------------------

# tomcatTomcat 7.0.57, 8091, "admin/admin" 

-----------------------------------------
build steps:

mvn clean package

sudo chmod 666 /var/run/docker.sock

# docker rm project -f

#  docker rmi project:1.0.0

docker build -t project:1.0.0 .

docker run -d --name project -p 8091:8080 project:1.0.0

docker commit project rajusw804/tomcat:$version

docker login --username ${dockerhubusername} --password ${dockerhubpassword}

docker push rajusw804/tomcat:$version

http://13.234.217.75:8080/github-webhook/
