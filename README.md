
Project Title: Corporate Asset Monitor <br/>
App Name: Asset Monitor
Project Overview:
The primary goal is to monitor corporate resources, including phones, tablets, laptops, and other equipment distributed to employees.
This application is designed to serve multiple organizations.
Each company has the flexibility to include some or all of its employees.
Companies and their staff can delegate one or more devices to employees for specific durations.
The application ensures that each company can track when a device was checked out and returned.
A detailed log is maintained for each device, recording its condition when it was issued and when it was returned.
Project Features:
I have set up a new virtual environment for this project and installed the necessary packages, as listed in the requirements.txt file. <br/>
Django Rest Framework has been utilized for developing the APIs. <br/>
The project employs a MySQL database. <br/>
Django ORM is used for all database operations. <br/>
Django Admin is utilized for creating the administrative panel. <br/>
Django Serializer is employed to create the serializers. <br/>
API documentation is generated using Django Rest Framework Spectacular. <br/>
Token-based authentication is implemented using Django Rest Framework Simple JWT. <br/>
Python coverage is used to generate coverage reports. <br/>
Tests are conducted using Pytest. <br/>
Pytest Factoryboy is used to create testing factories. <br/>
Bootstrap Admin is used to design the admin dashboard. <br/>
API testing is performed using Postman and Swagger. <br/>

Steps to Launch the Project:
Clone the project from the git repository. You can also download the zip file from the git repository, which includes a .env file for your convenience.
git clone https://github.com/MasumBhai/Corporate_Asset_Tracker_Django_REST_API.git
Create a virtual environment and activate it.
Install the required packages from the requirements.txt file.
Execute the following commands:
py manage.py makemigrations
py manage.py migrate --run-syncdb
py manage.py loaddata datadump.json
py manage.py createsuperuser
py manage.py collectstatic
py manage.py runserver
Open your web browser and access the following URL to perform API testing with Swagger:<br/>
URL: http://127.0.0.1:8000/api/schema/swagger-ui/
Authentication is required before performing any operations. To do so, access the token endpoint and provide your username and password in the request body. You will receive a refresh token and an access token in the response. Copy the access token and paste it into the Swagger authorization section. You can now perform operations.
URL: http://127.0.0.1:8000/token/
Access the admin dashboard at the following URL:
URL: http://127.0.0.1:8000/admin/
You can log in to the admin panel using the following superuser credentials to perform database operations:
Username: masum
Password: masum
Email: abdullahmasum6035@gmail.com
Tests can be run using the following command:
pytest
To view the coverage report, execute the following command and open the htmlcov folder, then open the index.html file:
coverage html
Access the API documentation at the following URL:
URL: http://127.0.0.1:8000/api/schema/redoc/
Database Structure:
This implementation comprises four primary models: Company, Device, Employee, and DeviceAssignment.<br/>

Company stores information about the companies utilizing the application.<br/>
Device represents corporate assets, including details such as their name, description, serial number, condition, and their association with a company.<br/>
Employee represents company staff, linked to a Django user through a one-to-one relationship and associated with the Device model via a many-to-many relationship, facilitated by the DeviceAssignment model.<br/>
DeviceAssignment records the allocation of devices to employees, with foreign keys to both the Device and Employee models, along with assignment and return dates.<br/>
Project Commands:
<details><summary><b>For Future Reference (Technical Details):</b></summary> 
For secret key generation:
python manage.py shell
from django.core.management.utils import get_random_secret_key
print(get_random_secret_key())
exit()

To create a data dump:
python3 manage.py dumpdata > datadump.json

For storing the secret key:
pip install python-dotenv

For Rest Framework Support:
pip install djangorestframework
pip install markdown
pip install django-filter

For API Documentation:
pip install drf-spectacular
py manage.py spectacular --color --file schema.yml

For Testing:
pip install coverage
coverage run -m pytest
coverage html
pip install pytest
pip install pytest-django
pytest -h
pip install pytest-factoryboy

To create a superuser:
py manage.py makemigrations
py manage.py migrate
python manage.py createsuperuser
py manage.py runserver

For Token-Based Authentication:
pip install djangorestframework_simplejwt

For Django Admin Dashboard:
pip install bootstrap-admin

For Storing Database Data:
For Storing Database Data: