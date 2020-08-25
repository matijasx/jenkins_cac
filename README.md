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

--- 
This will create Jenkins instance with already preconfigured items automatically set up in config/cac/jenkins.yaml :
- Admin account (username admin, password pw12) The initial password is specified in config/secrets/admin file, which could further be developed as temporary file fetched from secrets management app programatically.
- Imported git credentials to pull private repositories from my github account.
- Imported stdPipeline library
- Installed plugins from config/plugins.txt file to run Multibranch pipeline and Docker containers.

There is no need for manual steps to set up Jenkins, just run:
` docker-compose up --build ` from root folder of this repository.

Jenkins will load an example Multibranch pipeline as seed job. This pipeline is configured in config/cac/DemoJob.yaml and uses git credentials loaded during setup. This pipeline will scan application repository for Jenkinsfile and run further instructions specified there.
