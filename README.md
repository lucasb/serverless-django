# Serverless Django 3.1

This project is a minimal Django 3.1 setup which also ships the required `mysqlclient` binary with the application to enable Django to connect with an external MySQL database - while running serverlessly.

**Why do we need this?**

Running Django on serverless infrastructure was previously unheard of; now there are [guides/blog-posts](https://www.serverless.com/blog/django-serverless-framework-a-match-made-in-heaven) which detail how one can run Django on serverless infrastructure.

However most of the guides for serverless target Django2 (which is now outdated with LTS ending soon); additionally there is no documented guide/blog-post to **setup Django 3.1 on serverless** (at the time of writing).

To top it off, one would have **difficulties connecting to MySQL database** even if they did manage to get Django 3.1 running on  serverless due to missing `mysqlclient` binaries/libraries in the Lambda environment.

**Note:** The [same approach](./serverless.yml#L12-L19) could potentially be used to enable SQLite and PostgresQL connection support for serverless Django apps.

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

Run server at port **8000**: `python manage.py runserver`

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

## TODO

- [x] Repo setup
- [x] Readme completion (with instructions to run locally)
- [ ] Github Actions CICD
- [ ] Python linting and autopup8 support
- [ ] Support for multiple/local environments (AWS localstack via docker)
- [ ] Docker remote container setup
