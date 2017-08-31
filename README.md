# nordstrom_flask
### Flask for data science

The following is a step-by-step guide to the following:
 - Creating your flask dev environment
 - Deploying a basic flask app
 - Using Flask to train and predict with a model
 - Using a Bootstrap templates to add some style
 - jinja templating
 
# Creating your Flask Environment
## python 3

Install python 3
`brew install python3`

Set up the virtual environment
`virtualenv -p python3 venv3`

Activate the virtual environment
`source venv3/bin/activate`

Install flask
`pip3 install flask`

# A Basic Flask App
Import the needed things.
```python
from flask import Flask
application = Flask(__name__)
```

Add your first route. Routes tell flask what to do for different URLs. In this example, `yoursite:/` should trigger the `start() function and return 'Hello World!' to the webpage. 
```python
@application.route('/')
def start():
    return 'Hello World!'
```

Initialize your flask app.
```python
if __name__ == '__main__':
    application.debug = True
    application.run()
```

Start the application
`python application.py`

Check it out!

[Your Locally Running App](http://127.0.0.1:5000/)

# Now let's do some Data Science

We will be building a survival classifier using the [Titanic Survival Dataset](https://www.kaggle.com/c/titanic/data). 

The code to read in the data, split it up and train the model has already been written for you. We're going to focus on how to implement a training function 

When submitting a form, make sure to allow the POST method to be used with your route. 