# Simple Go-Docker-AWS project
This a simple Go project, dockerized with Docker, and deployed to AWS

## Technologies Used
* Go
* Docker
* AWS

## Dependencies

* Install Go - https://go.dev/doc/install
* Install Docker - https://docs.docker.com/get-docker
* Install docker-machine - https://github.com/docker/machine/releases
* Install AWS CLI - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
* Configure AWS CLI - https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html
* Create SSH Keys:
```
mkdir .ssh
cd .ssh
ssh-keygen
```


## Executing program
* Download the repository onto your computer and go to project file
```
git clone https://github.com/sayedh/go-docker-aws
cd go-docker-aws
```
* Use Docker-machine command to create a free instance in AWS
```
docker-machine create -d amazonec2 \
--amazonec2-region us-west-1 \
--amazonec2-ami ami-067f8db0a5c2309c0 \
--amazonec2-ssh-keypath ~/.ssh/id_rsa \
aws-new-cli-test
```
* Build and run the project
```
eval $(docker-machine env aws-new-cli-test)
docker build -t docker-test .
docker run -d -p 8080:8081 docker-test
```
* Get your instance Public IPv4 address from AWS

![image](https://user-images.githubusercontent.com/30685241/176921968-087a42c6-93ec-4670-9b95-4f7963d83284.png)


* Go to your browser and type http://YourInstancePublicIPv4Address:8080/ 

![image](https://user-images.githubusercontent.com/30685241/176922232-cdb8c1d9-c7cb-4e16-a9f2-17f2347d11d5.png)


* Next go to http://YourInstancePublicIPv4Address:8080/hi

![image](https://user-images.githubusercontent.com/30685241/176922254-97cc88af-2bdf-4418-9dd6-60c5b399b2ef.png)

