# flask-dashboard-template-2023

This is an example full stack web application built in Python with the [Flask](https://github.com/prof-rossetti/intro-to-python/blob/main/notes/python/packages/flask.md) framework. This application displays an interactive data dashboard of stock prices over time.

## Setup

### Prerequisites

To run this app, you'll need to have Anaconda, Python, and Pip installed (specifically Python version 3.10+).

### Installation

Make a copy of the template repository from GitHub. Clone your copy of the repo onto your local computer, for example onto your Desktop.

Navigate to the local repository from the command line, for example:

```sh
cd ~/Desktop/flask-dashboard-template-2023
```

> NOTE: it is important to navigate to the root directory before running any of the commands below.


Create new virtual environment (first time only):

```sh
conda create -n dashboard-env python=3.10
```

Activate the virtual environment (first time, or whenever you return to the project):

```sh
conda activate dashboard-env
```

> NOTE: it is important to activate the virual environment before running any of the commands below.

Install package dependencies (first time only):

```sh
pip install -r requirements.txt
```

> NOTE: if you see an error after running this package installation command, make sure you have first navigated to the root directory of your local repository, where the "requirements.txt" file exists.

### Services

You'll also need to obtain a "premium" access [AlphaVantage API Key](https://www.alphavantage.co/support/#api-key) and set it as the `ALPHAVANTAGE_API_KEY` environment variable (see configuration section below).


## Configuration

Create a new file called ".env" in the root directory of your local repository, and place inside contents like the following:


```sh
# this is the ".env" file...

# telling flask where our app is defined:
FLASK_APP="web_app"

# for interfacing with the AlphaVantage API:
ALPHAVANTAGE_API_KEY="________"
```

> NOTE: when you push your repository to GitHub, the ".env" file does not show up - this is desired behavior, as designated by the ".gitignore" file, to prevent our secret credentials stored in the ".env" file from being uploaded or exposed on GitHub.


## Usage

Test the data fetching process:

```sh
python -m web_app.services.alpha
```

Run the web application (then view in the browser at localhost:5000):

```sh
flask run
```

## Testing

Running tests, as configured by the "conftest.py" file and defined in the "test" directory:

```sh
pytest
```
