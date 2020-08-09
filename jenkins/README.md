# Jenkins

`full-ci-cd-practice/jenkins`

Docker container with preinstalled Java, Jenkins and Maven. Also contains docker-cli (because jenkins would build docker images too) whitch supposed to work with docker.sock from host, so just volume it.
Of course I would like to use a real AWS EC2 for that, but as I live in Crimea all I can it's just imagine like it's EC2.

### amazonlinux way

Build my docker image with Amazon Linux and jenkins installed

```
docker build --tag jenkins:ec2 ./jenkins
```

Run jenkins in docker

```
docker run --rm -d -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock jenkins:ec2
```

