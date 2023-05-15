# PiriLab 0.0.1


### Set Up Virtual Environment

1. Control Python

```
python --version 
```
or
```
python3 --version
```
2. Set Up Environment
```
python3 -m pip install --upgrade pip wheel setuptools
python3 -m virtualenv _venv
```
or 

```
python -m pip install --upgrade pip wheel setuptools
python -m virtualenv _venv
```
If you need install pip module :
```
sudo apt install python3-pip
```

3. Activate Environment
```
source _venv/bin/activate
```
or 
```
source _venv/local/bin/activate
```
If you need install virtualenv module:
```
sudo apt install python3-virtualenv
```

### Build Docker Container Environment 

1. Install Docker 

```
sudo apt update && sudo apt upgrade -y
sudo apt install docker.io -y
sudo usermod -aG docker $USER
newgrp docker
DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
mkdir -p $DOCKER_CONFIG/cli-plugins
```
2. Control Docker 
```
docker --version
```
3. Docker Image for RabbitMQ : https://hub.docker.com/_/rabbitmq/

```
docker pull rabbitmq
```

4. Run Docker Image 

```
docker run -it --rm --name rabbitmq -d -p 5672:5672 -p 15672:15672 rabbitmq:3.11-management
```

5. Control Docker Container

```
docker ps
```

### Using RabbitMQ Message Queue

If you will using RabbitMQ client you should install python pika module:
```
python -m pip install pika --upgrade
```

1. Send Message

```
python send.py
```

2. Receive Message 

```
python receive.py
``` 
