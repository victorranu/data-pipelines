# data-pipelines
A machine learning pipeline to categorize messages based on the needs communicated by senders. 

To execute code: 
create full conda environment: 
conda create -n env_full anaconda python=3.5

To activate this environment, use

    $ conda activate env_full

To deactivate an active environment, use

    $ conda deactivate

needs command line arguments
start from folder: Project2_disaster_response_pipeline_project

build ETL pipeline that processes messages(csv) and category data(csv),
and loads into SQLite database; messages, categories, database from command line:
$ python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db

and then a machine learning pipeline reads from database to create
and save a multioutput supervised learning model:
$ python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl

then web app extracts data from database to provide data visualizations and 
use model to classify new messages for 36 categories:
cd app
$ python run.py

machine learning helps different organizations understand which messages are 
relavent and which to prioritize, it helps find messages that matter and 
use basic word searches to provide trivial results. 

