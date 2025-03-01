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



