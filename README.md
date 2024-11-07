## OPENAI
You first need to create an account on openAI and get your openAI key

## How to Use (Docker)

```sh
cd DrugPredictor
docker build -t predictor-docker:latest .
#if you want to make sure Docker is build fresh new no cache
docker build --no-cache  -t predictor-docker:latest .
docker run -it -p 9999:9999 predictor-docker
##this should start the web app

########### no need for this ######
conda activate python_env

sk-proj-XXXXXXXXXXXXX (USE YOUR API KEY)
```

# How to run the code

```sh
cd DrugPredictor
python drug_extractor_agent.py
   # DrugInteractionAgent


####Run with Docker and flask
docker build --no-cache  -t predictor-docker:latest . 
docker run -it -p 9999:9999 predictor-docker /bin/bash
conda activate python_env

python app.py

## Deploying on Heroku
 docker buildx build --provenance=false --platform linux/amd64 -t predictor-docker-linux:latest .
 docker tag predictor-docker-linux registry.heroku.com/drug-predictor1/web
 docker push registry.heroku.com/drug-predictor1/web 
 heroku container:release web -a drug-predictor1


 #to delete all docker containers and clear cache
 docker system prune --all
 