# snowflake-ai-sql-audio-parsing
This project demonstrates how to use Snowflake AISQL functions to transcribe audio, mine unstructured data, translate text, redact sensitive content, and compare image embeddings — all inside the Snowflake Notebook UI.

By [Meriel O'Conor](https://www.linkedin.com/in/merieloconor/)
<br/><br/>
**Contents**
- [Notebook](#notebook)
- [Audio Files](#audio-files)
- [Image Files](#image-files)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
<br/><br/>
## Notebook
📓 AI_SQL Demo 11_19_25.ipynb

A Snowflake Notebook-style workflow containing:

Audio transcription using AI_TRANSCRIBE

Text translation with AI_TRANSLATE

Redaction using AI_REDACT

Image parsing and embedding comparison

**Note**: GitHub renders this notebook as a Jupyter file, so **Snowflake-specific metadata** (like named cell references) **does not always display cleanly**.
<br/><br/>
## Audio Files
🎧 (audio_files/)

Open-source audio recordings from LibriVox: Hansel and Gretel, Rumpelstiltskin

Used to demonstrate transcription and text processing.
<br/><br/>
## Image Files
🖼 (img_files/)

AI-generated images related to the stories, used to showcase: image parsing and similarity comparison
<br/><br/>
## Requirements
**Snowflake** account only 
<br/><br/>
A trial or full Snowflake account is required.

Sign up: https://signup.snowflake.com/. 

Takes 1 minute to create a free trial account that lasts 30 Days and comes with $400 of credit.

The notebook runs successfully using:
ACCOUNTADMIN on a trial account
(Other roles may require additional privileges to create databases, stages, or use AI functions.)

It runs fine with an XS warehouse.

Local / GitHub Environment
No local environment setup is required for running the Snowflake notebook itself.

## Other notes
The notebook relies on named SQL cells, which are not rendered visibly in standard notebook preview in GitHub. When in Snowflake, these appear clearly and allow Python cells to reference SQL cells by calling the name of the cell. 

You can see the cell metadata name in the CODE notebook view. 

For example this cell is called AI_EXTRACT_CELL and can be referenced later in a Python cell by just writing AI_EXTRACT_CELL.

  {
   "cell_type": "code",
   "id": "efad8002-e764-4eb6-98c3-1897930c92db",
   "metadata": {
    "language": "sql",
    "name": "AI_EXTRACT_CELL"
   },
   "outputs": [],
   "source": "SELECT\n    AI_EXTRACT(\n        text => AUDIO_VARCHAR,\n        responseFormat => {\n            'character': 'Who are the main characters in the story?',\n            'author': 'Who wrote the story?',\n            'denouement': 'What is the story\\'s denouement?'\n        }\n    )\nFROM SNOWFLAKE_LEARNING_DB.AUDIO_TESTING.RAW_AUDIO;\n",
   "execution_count": null
  }

You can now integrate Snowflake with GitHub and directly pull and push via the Snowflake UI https://docs.snowflake.com/en/developer-guide/git/git-overview. I did this and it worked well.
<br/><br/>
## How to Run
1. Open Snowflake Notebook UI
2. Select 'import .ipynb file' and upload the notebook
3. Run cells in order

_Project started 11/14/25_
