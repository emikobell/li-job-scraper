# LinkedIn Job Scraper

This tool scrapes LinkedIn job postings using Python, Selenium, and BeautifulSoup. The information gathered is stored in a Cloud Firestore database. The information gathered are:
- Job ID
- Position Title
- Company Name
- LinkedIn Job Level
- Job Description in string format

## Tech Stack

- Python 3
- Selenium Web Driver
- BeautifulSoup 4
- Firebase DB (on Cloud Firestore)

## Installation

### Requirements
- Python 3.9
- Cloud Firestore credentials
- Chrome driver

### Steps

1. Clone the github repository.
```zsh
git clone https://github.com/emikobell/li-job-scraper
```

2. Create a virtual environment using virtualenv.
```zsh
virtualenv env
```

3. Activate the virtual environment.
```zsh
source env/bin/activate
```

4. Install the dependencies provided in requirements.txt.
```zsh
pip3 install -r requirements.txt
```

5. Create a secrets.py file to save your LinkedIn username and password.
gather_data.py will be importing the following:
```python
li_username = 'abc123'
li_pass = 'abc123'
```

6. Have the Firestore project credentials.json in the working directory.

7. Edit database.py to reflect your database information. E.g.:
```python
cred = credentials.Certificate('your-cred-here.json')
```

8. Edit gather_data.py with a list of your desired locations in the US to search.
For example, the current location list currently contains US states.

9. Run gather_data.py.
```zsh
python3 gather_data.py
```

10. Let Selenium run in the background while the data is scraped.
**Note** If your computer is in sleep/screensaver mode, Selenium will shut down.
The browser window must be active for this to continue running.