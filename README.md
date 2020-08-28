# Serverless Django 3.1

Serverless Django with MySQL database setup; hosted on AWS lambda using serverless framework

## Pre-requisites

Python3.8

- Install [Virtualenv](https://docs.python.org/3/library/venv.html) globally (reccomended)\
  `pip install virtualenv`
- Initialise virtualenv in current directory\
  `virtualenv venv`
- Activate virtualenv\
  `source venv/bin/activate`
- Install local dependencies (to venv):\
  `pip install -r requirements.txt`

### Deployment Pre-requisites

Node (lts):

- Install serverless plugins dependencies:\
  `npm install`

## Development

Run server: `python manage.py runserver`

## Deployment

Deployments will be administered and automated via CICD pipeline (Github Actions).

However, to manually deploy perform the following steps:

```sh
python manage.py collectstatic --noinput
sls deploy
```

## Testing

TODO

## Admin

You can view django admin interface at `http://localhost:8000/admin`
