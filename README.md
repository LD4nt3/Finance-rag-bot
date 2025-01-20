# Finance-rag-bot
An AI-powered financial advisor using RAG (Retrieval Augmented Generation) for stock market analysis and investment decision support. The application leverages real-time data through FMP API integration and advanced language models to provide informed financial insights.

## Overview

This application combines the power of Large Language Models (LLMs) with Retrieval Augmented Generation (RAG) to provide accurate, context-aware financial advice and market analysis. By incorporating real-time data from the Financial Modeling Prep (FMP) API, the system ensures that recommendations are based on current market conditions.

### Key Features

- Real-time stock market data integration via FMP API
- RAG-enhanced language model responses
- Interactive web interface built with Streamlit
- Vector database (Qdrant) for efficient information retrieval
- Docker containerization for easy deployment

## Technology Stack

- **Frontend**: Streamlit
- **Database**: Qdrant (Vector Database)
- **Infrastructure**: Docker & Docker Compose
- **Programming Language**: Python 3.10
- **API Integration**: Financial Modeling Prep (FMP)

## Usage

1. Access the Streamlit interface through your web browser
2. Input your financial queries or analysis requests
3. Receive AI-powered recommendations backed by real-time market data


## RAG Implementation

The application implements Retrieval Augmented Generation to enhance the accuracy and reliability of AI responses. RAG provides several key benefits:

- **Reduced Hallucinations**: Grounds AI responses in factual, real-time data
- **Enhanced Accuracy**: Verifies information before generating responses
- **Broader Knowledge Base**: Combines LLM capabilities with external data sources
- **Contextual Understanding**: Improves response relevance through better context awareness

## Project Workflow
![Workflow](https://cdn.discordapp.com/attachments/546555224068849665/1325835722631942239/IMG_8173.png?ex=677d3c3d&is=677beabd&hm=58e7bd810fb6930a632d54962e4fbde517744f3ca12a1942b64a85645c89a3a6&)


## Installation & Setup

### Prerequisites

- Docker
- Docker Compose
- FMP API key
- Environment variables configured in `.env` file

## Project Structure

```
.
├── src/
│   └── main.py
├── .env
├── docker-compose.yml
├── Dockerfile
└── requirements.txt
```

## Configuration

### Docker Compose Services

#### Application Service
- Built from local Dockerfile
- Mounts `.env` file for configuration
- Runs Streamlit server on port 8501

#### Qdrant Service
- Vector database for efficient data retrieval
- Exposed ports: 6333, 6334, 6335
- Persistent storage in `./qdrant_data`
- Configured with INFO level logging

### Running the Application

<details close>
    <summary>Run using a Docker container locally</summary>
<br>

> Important Notes: Make sure that you install `Git`, `Docker` and `Python` in your local environment

1. Open your development environment
2. Using a terminal, run a `git clone <repo_url>`
3. Navigate to the directory repo using your terminal
```bash
cd ./route/to/repo
```
4. Create a `.env` file inside the repository folder with the following variables
```python

AZURE_OPENAI_API_KEY = ''

AZURE_OPENAI_ENDPOINT = ''
AZURE_DEPLOYMENT = ''
AZURE_VERSION = ''

AZURE_OPENAI_ENDPOINT_EMBEDDINGS = ''
AZURE_DEPLOYMENT_EMBEDDINGS = ''
AZURE_VERSION_EMBEDDINGS = ''

FMP_API_KEY= ''
```
5. Using the terminal in the repository route run `docker compose build` to create the image that the container is going to use.
6. Run `docker image ls -a` to double check that the docker image was build and it's available to run the docker container.
7. In your terminal run
```bash
docker compose up --build
```
The application will be available at `http://localhost:8501`

</details>


<details close>
    <summary>Run using a Docker container in Lightning</summary>
<br>

1. Go to the top menu, `Terminal` > `New Terminal`
2. Run a `git clone <repo_url>`
3. `cd <repo>`
4. In the root of the repository create the `.env` file with the environmental variables
```python
AZURE_OPENAI_API_KEY = ''

AZURE_OPENAI_ENDPOINT = ''
AZURE_DEPLOYMENT = ''
AZURE_VERSION = ''

AZURE_OPENAI_ENDPOINT_EMBEDDINGS = ''
AZURE_DEPLOYMENT_EMBEDDINGS = ''
AZURE_VERSION_EMBEDDINGS = ''

FMP_API_KEY= ''
```
5. In the terminal run `docker compose build` to create the image that the container is going to use.
6. Once the image is build, click on the streamlit plugin
7. Click on `+ New App`
8. Add the following command instead of the `streamlit command`:
```bash
streamlit run --server.port 8501 ["your folder"]/src/main.py
```
9. Click on the `Run` button on the right bottom corner

</details>


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
