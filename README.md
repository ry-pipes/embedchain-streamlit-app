# 

This repo serves as a template for how to deploy a LangChain on Streamlit.


## Deploy on Streamlit

This is easily deployable on the Streamlit platform.
Note that when setting up your StreamLit app you should make sure to add `OPENAI_API_KEY` as a secret environment variable.


<h1 align="center">
📖 LangChain-Streamlit-Docker App Template
</h1>

## 🔧 Features

- Basic Skeleton App configured with `openai` API
- A ChatBot using LangChain and Streamlit
- Docker Support
- Deployment on Streamlit 
- Deployment on Google Cloud App Engine

This repo contains an `main.py` file which has a template for a chatbot implementation.

## Adding your chain
To add your chain, you need to change the `load_chain` function in `main.py`.
Depending on the type of your chain, you may also need to change the inputs/outputs that occur later on.


## 💻 Running Locally

1. Clone the repository📂

```bash
git clone https://github.com/amjadraza/langchain-streamlit-docker-template.git
```

2. Install dependencies with [Poetry](https://python-poetry.org/) and activate virtual environment🔨

```bash
poetry install
poetry shell
```

3. Run the Streamlit server🚀

```bash
streamlit run app/main.py 
```

Run App using Docker
--------------------
This project includes `Dockerfile` to run the app in Docker container.

Build the docker container

``docker  build -t langchain-chat-app .``

1. Run the docker container directly 

``docker run -d --name langchain-chat-app -p 8080:8080 langchain-chat-app ``

2. Run the docker container using docker-compose (Recommended)

``docker-compose up``

Deploy App on Streamlit Public Cloud
------------------------------------
This app can be deployed on Streamlit Public Cloud using GitHub. Below is the Link to 
Publicly deployed App


Deploy App on Google App Engine
--------------------------------
This app can be deployed on Google App Engine following below steps.

## Prerequisites

Follow below guide on basic Instructions.
[How to deploy Streamlit apps to Google App Engine](https://dev.to/whitphx/how-to-deploy-streamlit-apps-to-google-app-engine-407o)

We added below tow configurations files 

1. `app.yaml`: A Configuration file for `gcloud`
2. `.gcloudignore` : Configure the file to ignore file / folders to be uploaded

I have adopted `Dockerfile` to deploy the app on GCP APP Engine.

1. Initialise & Configure the App

``gcloud app create --project=[YOUR_PROJECT_ID]``

2. Deploy the App using

``gcloud app deploy``

3. Access the App using 

https://pandasai-app.ts.r.appspot.com/

## Report Feedbacks

As `langchain-streamlit-docker-template` is a template project with minimal example. Report issues if you face any. 

## DISCLAIMER

This is a template App, when using with openai_api key, you will be charged a nominal fee depending
on number of prompts etc.