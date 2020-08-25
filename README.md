Prerequisites for running Jenkins instance:
- Clean Ubuntu or other Debian distribution
- Docker installed: `
	sudo apt-get update
	sudo apt-get install \
	    apt-transport-https \
	    ca-certificates \
	    curl \
	    gnupg-agent \
	    software-properties-common
	sudo usermod -aG docker jenkins
	sudo chmod 666 /var/run/docker.sock
`
Run using `docker-compose up --build`