### Circleci Badge Status
[![ehino](https://circleci.com/gh/ehino/devopsmircoservices.svg?style=svg)](https://app.circleci.com/pipelines/github/ehino/devopsmircoservices)

## Project Summary
The goal of this project goal was to operationalize a Machine Learning Microservice API using kubernetes. 

### Running Scripts
In other to run the python scripts and the web application, certain steps had to be carried out:
1. Creating and setting up virtual environment
        python3 -m venv ~/.devops
        source ~/.devops/bin/activate
2. Installing the necessary dependencies such as Docker, Hadolint, Kubernetes (Minikube)
        Hadolint (Ref: https://tcoil.info/how-to-install-hadolint-on-linux/): 
            sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3       hadolint-Linux-x86_64

            sudo chmod +x /bin/hadolint
        Docker (Ref: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04):
            sudo apt install apt-transport-https ca-certificates curl software-properties-common
            curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
            sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
        
        Kubernetes(Ref: https://minikube.sigs.k8s.io/docs/start/)
            curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
            sudo install minikube-linux-amd64 /usr/local/bin/minikube
            
3. ### Running `app.py`

        1. Standalone:  `python app.py`
        2. Run in Docker:  `./run_docker.sh`
        3. Run in Kubernetes:  `./run_kubernetes.sh`

## Files in repo
        1. Standalone:  `python app.py`
        2. Run in Docker:  `./run_docker.sh`
        3. Run in Kubernetes:  `./run_kubernetes.sh`
        4. Makefile: Environment setup and lint testing
        5. Requirements.txt: Necessary dependencies to run the app
        6. make_predictions.sh: bash script which runs machine learning model and make housing prices predictions
