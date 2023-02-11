sudo su
apt update
apt install openjdk-11-jr
java -version

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null

apt-get update 
apt-get install jenkins
systemctl enable jenkins
systemctl start jenkins                         //Jenkins Works On port no. 8080

unlock jenkins and install Suggested Plugins 

sudo systemctl status jenkins


sudo apt install nodejs
sudo apt install npm
npm install 

node app.js                      //App will start working. 
		     // Add Port no. 8000 for accessing it.	


{To-Do App will be working at node IP:8000}


now, Automating all of the above using Docker

sudo apt install docker.io
 
//Docker baseimage with nodeJs

vi Dockerfile
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
EXPOSE 8000
CMD ["node","app.js"]

sudo usermod -a -G docker $USER
//reboot

docker build . -t node-app
docker run -d --name node-todo-app -p 8000:8000 todo-node-app
