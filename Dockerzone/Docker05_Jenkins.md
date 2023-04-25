### Create a Jenkins Image on my own Dockerfile

* Take a EC2 Machine
* Install Docker (or) using Docker playdround
* Follow the below commands
* vi Dockerfile
```Dockerfile
FROM ubuntu:22.04
LABEL author="Laxman Narayana" organization="QualityThought" project="learning"
RUN apt update && apt install openjdk-11-jdk maven curl -y
RUN curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
RUN echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
RUN apt-get update && apt-get install jenkins -y
EXPOSE 8080
CMD ["/usr/bin/jenkins"]
```
`docker image build -t jenkins .`
