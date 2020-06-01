# model-logger

![model-logger Logo Header](https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/logo-header.png)

``model-logger`` is a Python library for storing model's profile and rapid inter model comparision. Powered by ``dash`` and ``SQLITE3``,
It's compact ,light weight ,interactive yet powerful tool to gain useful insights.  

## Installation

### Using pip

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install model-loger.

[![PyPi Downloads](https://pepy.tech/badge/modellogger)](https://pepy.tech/badge/modellogger)
[![PyPi Monthly Downloads](https://pepy.tech/badge/modellogger/month)](https://pepy.tech/badge/modellogger/month)
[![PyPi Version](https://badge.fury.io/py/modellogger.svg)](https://pypi.org/project/modellogger/)

```bash
pip install modellogger
```

## Initialization

```python
from modellogger.modellogger import ModelLogger

#initialise a modelloger instance
path = "c/path/to/db/databasename.db"
mlog = ModelLogger(path) #setup complete
 
```

If you are already using a db created by modelloger you can directly load it by stating it's path
If you are creating a new project just give location where you want to store the db followed by a name.db .

Now you are ready to rock and roll.
Out of the box you will have the following functionalities:
| Filename | Requirements|
|----------|-------------|
| store_model| Store the model as fast as you can click .Compatible with all sklearn models |
| delete_model| Used to delete specific model record |
| delete_all | Deletes all model records present in the log |
| view_results| Returns mini result in the form of a dataframe |
|model_profiles| Create a model summary sheet where you can play and gain insights from the different models |


<img alt="model-logger" src="https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/modellogger-setup.gif" width="800" />


## Usage

### `store_model()`

``save_pickle`` : let's you save the model as a pickle file with model_name as the
file name . Uses joblib for pickling ,to use it later use joblib.load('name').

``model_name ``: Give a unique name to your model.

``columns`` :Columns used for tranning the model.

``accuracy`` : Scores to measure the performance eg. rmse , mse , logloss or a custom function that returns a metric.
           Ideally same factor across all models will help gaining insights from summary.

``Flag`` : If true than will print out the contents of the db.   

`model-logger` currently stores the following attribute:

- Model id
- Model name(given by user)
- Scores
- Number of columns
- Feature set used for tranning the model
- model parameters
- Train size
- Number of continuous variables
- Number of catagorical variable
- Model type
- Model name

#### Example
```python
 gboost = GradientBoostingClassifier() 
 gboost.fit(X_train,y_train) 
 mlog.store_model('my_model_name',gboost,X_train,1.0) 
 #alternatively
 mlog.store_model('my_model_name',gboost,X_train,get_score(gboost),save_pickle = True)

```

<img alt="model-logger" src="https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/model-store.gif" width="800" />


### `view_results()` 

``generate_csv``: If true than generate the report in the form of a csv

``csv_name``: Name of the csv file , default -- Model_Report.csv

#### Example
```python

mlog.view_results(True,'my_report')

```

<img alt="model-logger" src="https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/view-results.gif" width="800" />


### `delete_model()`

``Model_name`` : name of the model you want to delete –> use view_results() for referece

``Model_id`` : id of the model –> use view_results() for referece Flag : If true than will print out the contents of the db.

#### Example
```python

mlog.delete_model(Model_name = "Mymodel") 
mlog.delete_model(Model_id = 1)

```

### `delete_all()`

``Flag`` : If true than will print out the contents of the db.

#### Example
```python

mlog.delete_all()

```

<img alt="model-logger" src="https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/model-delete.gif" width="800" />


### `model_profiles()`

``batch_size`` :  How many entries to consider at once while comparing via graphs
                  If batch_size less than total number of entries , than it will 
                  grouped into different pages . Different pages will have different
                  graphs .If "All" is used than it will consider all the entries at once

``port``: use to change the port number in which the server is running. 

``debug``: If true than run the server in debug mode

#### Note:

``Do not`` run in debug mode while using it in jupyter notebook 
``For jupyter notebook`` click on ``kernel/interrupt`` to stop the server .  
``for cmd/anaconda prompt`` ----> use ``[ctrl+c]`` to stop the server .

#### Example
```python

mlog.model_profiles('All')
mlog.model_profiles(5)

```
## Fun Part 
All the ``graphs`` and ``insights`` are interlinked with the ``datatable`` .
You can do the following operations out of the box and the graphs will change dynamically (as long as the server is running) :

| Operation | operator|
|----------|-------------|
|'greater than equal too '| '>='|
|'less than equal too '| '<='|
|'less than '| '<'|
|'greater than '| '>'|
|'not equal too '| '!='|
|'equal too '| '='|
|str search |'contains '|
| date serach|'datestartswith '|


<img alt="model-logger" src="https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/model-profiles.gif" width="800" />


## Support `model-logger`

The development of ``model-logger`` relies completely on contributions.

#### Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## First roll out 
*May 31, 2020 💘*

## License
[apache-2.0](https://choosealicense.com/licenses/apache-2.0/)


![model-logger Logo footer ](https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/end.png)