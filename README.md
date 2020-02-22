# disaster-pipeline

## Table of Contents
1. [Project Introduction and motivation](#Project-Introduction-and-motivation)
2. [Instullation](#Instullation)
3. [File Description](#File-Description)
4. [Results](#Results)
5. [Licensing, Authors, and Acknowledgment](#Licensing-Authors-Acknowledgment)
6. [Instructions](#Instruction)

### Project Introduction and motivation <a name="Project Intorduction and motivation"></a>

### Instullation <a name="instullation"></a>

### File Description <a name="File Description"></a>

### Results <a name="Results"></a>

### Licensing, Authors, and Acknowledgment <a name="Licensing, Authors, and Acknowledgment"></a>


### Instructions <a name="instructions"></a>
1. Run the following commands in the project's root directory to set up your database and model.
    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`
2. Run the following command in the app's directory to run your web app.
    `python run.py`
3. Go to http://0.0.0.0:3001/
