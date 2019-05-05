# django_allauth

virtualenv -p python3 env
pip install django
pip install django-allauth

django-admin startproject project
python manage.py migrate
python manage.py runserver

#(env)project/settings.py
Add the django-allauth at settings.py

INSTALLED_APPS = [
	...
	'django.contrib.sites',
	'allauth',
	'allauth.account',
        'allauth.socialaccount',
        'allauth.socialaccount.providers.github',
]


AUTHENTICATION_BACKENDS = (
        "django.contrib.auth.backends.ModelBackend",
        "allauth.account.auth_backends.AuthenticationBackend",
        )

SITE_ID = 1

LOGIN_REDIRECT_URL = 'home'

#(env)project/urls.py
....
	path('accounts/', include('allauth.urls')),
...

python manage.py migrate

Remplir le formulaire https://github.com/settings/applications/new 	

Plus d'info sur https://wsvincent.com/django-allauth-tutorial/
