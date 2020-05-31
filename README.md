# Modelloger

![Pandas Profiling Logo Header](https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/logo-header.png)

Modelloger is a Python library for storing model's profile and rapid inter model comparision. Powered by dash and SQLITE3,
It's compact ,light and interactive yet powerfull tool to gain usefull insights.  

## Installation

### Using pip

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install modelloger.

[![PyPi Downloads](https://pepy.tech/badge/modellogger)](https://pepy.tech/badge/modellogger)
[![PyPi Monthly Downloads](https://pepy.tech/badge/modellogger/month)](https://pepy.tech/badge/modellogger/month)
[![PyPi Version](https://badge.fury.io/py/modellogger.svg)](https://pypi.org/project/modellogger/)

```bash
pip install modellogger
```

## Usage

```python
from ModelLog import ModelLogger

#initialise a modelloger instance
path = "c/path/to/db/databasename.db"
mlog = ModelLogger(path)
 
#If you are already using a db created by modelloger you can directly load it by stating it's path
#if you are creating a new project just give location where you want to store the db followed by a name.db  
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/apache-2.0/)