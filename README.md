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

