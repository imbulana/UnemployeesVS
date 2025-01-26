# UnemployeesVs

## Setup (Backend)

Create a conda environment with python 3.11

```bash
conda create -n hunter python=3.11 -y
conda activate hunter
```
Install the required packages
```bash
python3 -m pip install -r requirements.txt
```

Setup Docker using the instructions found [here](https://docs.docker.com/engine/install) if you do not already have Docker set up

To use docker within the conda environment, and user to docker group

```bash
sudo usermod -aG docker $USER
newgrp docker
docker ps # verify that you have acces to docker
```

Create a `.env` following the `.env-example` with your openAI and LangChain API keys entered

Additionally, navigate to `backend/deployment` and create a `docker-compose.yml` file following the `docker-compose-example.yml` file with the API keys filled in

## Deploy (Backend)

Deploy with LangGraph

```bash
cd backend/deployment
langraph built -t hunter-test
docker compose up
```

Sign into [LangSmith website](https://smith.langchain.com/) on your browser and navigate to the LangGraph Platform tab and launch LangGraph Studio

![LangGraph Studio](assets/langgraph_studio.png)