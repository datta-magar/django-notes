# django-notes
Testing in Django (Django test framework)
Based on the unittest library
django add features:
test-client dummy web browser
simulate authentication
temporary database
django test framework adds features:
api test client

where do you put test?
placeholder tests.py added to each app
Or create tests/ subdirectory to split tests up
Keep in mind:
Only use either tests.py or tests/ (not both)
Test modules must start with test_
test derectory must contain __init__.py

Test database
test code that uses the DB
specific database for tests
runs test -> clears data -> repeat
happens for every test by default in django test framework

Test classes
SimpleTestCase:
no database integrastion
useful if no database is required for your test
TestCase:
Database integration
Useful for testing code that uses database

test command
% python manage.py test

Mocking
overide or change behaviour of dependancies
avoid unintented side effects
isolate code being tested

why use mocking
avoid relying on extarnal services
cant gaurenty they will be availble
makes tests unprdictable
avoid unintended consequances
accidently sending emails
overloading ecxtarnal services

example
register_user() -> create_in_db() -> send_welcome_email() -> email sent
prevent email being sent 
ensure send_welcome_email() called correctly
Another benefits
spped up tests

how to mock code
use unittest.mock (built python)
MagicMock/Mock - replace real object
patch - overrides code for test

Testing web requeasts (APIs)
make actual requests
django rest framework gives APIClient
make requests
check result
override authentication

common testing problems

COnfigure Database
PostgreSQL
popular open source DB
integrates well with django
docker compose
defined with project reusable
persistant data using volumes
handles network configuration
environment variable configuration

Network connectivity
set depends_on on app service to start db first

steps for configuring database
configure django
tell django how to connect
install database adopter dependancies
install the tool django uses to connect
update python requirements

django needs to know
engine (type of database)
hostmname (ip or domain name for database)
port 
database name
username
password
defined in settings.py file

envoronment variables
pullconfig values from environment variables
easily passed to docker
used in local dev or prod
single place to configure project
easy to do with python
% os.environment.get('DB-HOST')

Psycopg2 - the package that you need in order for django to connect to our database
most popular postgresql adaptor for python
supported by django
installetion options
psycopg2-binary
OK for development
not good for production
Psycopg2
compiles from source
required additional dependancies
easy to install with docker

installing Psycopg2 
List of package dependancies in docs
C compiler
python-3 dev
libpq-dev
equivalent packeges for alpine
postgres-sql client
build-base
postgres-sql-dev
musl-dev
found by searching and trial and error
docker best practice:
clean up build dependancies


