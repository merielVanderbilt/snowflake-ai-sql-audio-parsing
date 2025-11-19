# snowflake-ai-sql-audio-parsing
This project demonstrates how to use Snowflake AI_SQL functions to transcribe audio, mine unstructured data, translate text, redact sensitive content, and compare image embeddings — all inside the Snowflake Notebook UI.

By Meriel O'Conor https://www.linkedin.com/in/merieloconor/

Contents

📓 Notebook
AI_SQL Demo (YYYY-MM-DD).ipynb
A Snowflake Notebook-style workflow containing:

Audio transcription using AI_TRANSCRIBE

Text translation with AI_TRANSLATE

Redaction using AI_REDACT

Image parsing and embedding comparison

Note: GitHub renders this notebook as a Jupyter file, so Snowflake-specific metadata (like named cell references) does not always display cleanly.

🎧 Audio Files (audio_files/)

Open-source audio recordings from LibriVox:
Hansel and Gretel
Rumpelstiltskin

Used to demonstrate transcription and text processing.

🖼 Image Files (img_files/)

AI-generated images related to the audio stories, used to showcase:

image parsing
similarity comparison

Requirements: Snowflake
A trial or full Snowflake account is required.
Sign up: https://signup.snowflake.com/

The notebook runs successfully using:
ACCOUNTADMIN on a trial account
(Other roles may require additional privileges to create databases, stages, or use AI functions.)

It runs fine with an XS warehouse.

Local / GitHub Environment
No local environment setup is required for running the Snowflake notebook itself.

Hints & Notes
The notebook relies on named SQL cells, which are not rendered visibly in standard Jupyter previews.

When in Snowflake, these appear clearly and allow SQL cells to reference each other via templates like {{CELL_NAME}}.

Project started 11/14/25
