# QA-Bot-INLPT-WS2023

### Our Team:

Sharma, Shivangi, M.Sc Data and Computer Science

Gudibandi, Shreeharsh Ashok, M.Sc Data and Computer Science

Chaturvedi, Suryansh, M.Sc Data and Computer Science

Schmid, Janik, M.Sc Data and Computer Science


## Installation guide:

### Running the RAG pipeline
All steps needed to run our RAG pipeline using the preprocessed data and the database we already created:

If you have a GPU available, you can just start with step 3 after opening the notebook `QnA_system.ipynb`.

1. **Open the Jupyter Notebook**:
   - Open the Jupyter Notebook named `QnA_system.ipynb` in google colab.

2. **Add `.env` File**:
   - Upload the `.env` file you find in the repository to google colab

3. **Add `Search results 20240102.csv` File**:
   - Upload the `Search results 20240102.csv` file you find in the repository to google colab

3. **Run All Cells**:
   - Run all cells in the notebook to ensure that all necessary code blocks are executed and variables are properly initialized.

4. **Execute the Last Cell**:
   - The last cell of the notebook will prompt you to submit your queries, each separated by a new line.

5. **Input Queries**:
   - Input your queries one by one hit submit after you enter them.

### Downloading data and creating the database
Only needed if you want to set up everything on your own:


#### Creating lines.csv

This is a table containing all the lines of all files of the data we are using. To create it you just need to run the notebook `AnalyzeFromHtml.ipynb` that you find in the DataAcquisition directory. The required libraries are located inside the first cell of the module.

#### Creating chunks.csv

This is a table containing the chunks we are using for our text retrieval system. To create it you need to run the notebook `Chunking.ipynb` that you find in the DataAcquisition directory. The required libraries are located inside the first cell of the module. In addition you need to have a file `.env` inside the DataAcquisition directory. It should contain your Huggingface api key and look like this:
```
HF_AUTH="<--your-key-->"
```
You can also take the .env file you find in our repository for that

#### Creating the vector database

Our vector database is on Pinecone and credentials of the account used can be found in the .env file under the DataIntegration directory. It contains your Huggingface and Pincone api keys and Pinecone environment which should look like this:
```
HF_AUTH=""<--your-key-->"
PINECONE_API_KEY="<--your-key-->"
PINECONE_ENVIRONMENT=""<--your-environment-->"
```

To set up database you need to run the notebook `ChunksEmbeddingsAndPineconeDB.ipynb` that you will find under same directory. The required library for Pincone is the notebook itself. In addition, you will require to load 'chunks.csv' (under DataAcquisition directory) to create embeddings for the data chunks and .env file to connect to Pinecone environment.
