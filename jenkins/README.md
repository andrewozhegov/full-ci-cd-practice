# Jenkins

`full-ci-cd-practice/jenkins`

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

