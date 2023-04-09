# Jenkins_Setup
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \ /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \ https://pkg.jenkins.io/debian-stable binary/ | sudo tee \ /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins

sudo cat /var/lib/jenkins/secrets/initialAdminPassword


# Docker_File

FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
RUN npm run test
EXPOSE 8000
CMD ["node","app.js"]

# Run_Docker_Container

sudo usermod -a -G docker $USER
sudo reboot
docker build . -t node-app
docker run -d --name node-todo-app -p 8000:8000 node-app


# node-todo-cicd

Run these commands:


`sudo apt install nodejs`


`sudo apt install npm`


`npm install`

`node app.js`


