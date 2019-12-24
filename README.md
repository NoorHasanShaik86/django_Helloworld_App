# django_Helloworld_App

# Installation of Django
1. Install python 3 on your pc (sudo apt install python3).
2. run  " python --version " to know the version of python in your pc.
3. Install pip on your pc (sudo apt install pip).
4. TO know the version of pip run the command " pip --version ".
5. TO install Django run the command " pip install Django==2.0.5 ",
6. To install another version just change the numbers at the end.
7. IF you found any errors while you run the above command about local settings run the following commands to reconfigure local settings
8. '' export LANGUAGE=en_US.UTF-8
      export LANG=en_US.UTF-8
      export LC_ALL=en_US.UTF-8
      locale-gen en_US.UTF-8
      dpkg-reconfigure locales   "
      
9. TO know the version of Django the you have installed run the command " django-admin --version ".



# Creating a Hello World app

1. First create a folder hello world project folder on Desktop.
2. To create that folder run the following commands.
        cd Desktop
        mkdir helloworld
        cd helloworld
        
3. To create a app first we need to create a virtual environment. Initially ther will be no virtual environment.
4. To create virtual environment run the command " pipenv ".
5. After creating the virtual environment to enter into that ru the command " pipenv shell ".
6. Create a new Django project called helloworld_project making sure to include the period (.) at the end of the command so that it is installed in our current directory.
            django-admin startproject helloworld_project .
7. To see the files in the helloworld_project run the command " tree ".
8. In helloworld_project there are different files, in that
    i) The settings.py file controls our project’s settings
    ii) urls.py tells Django which pages to build in response to a browser or url request
    iii)  wsgi.py, which stands for Web Server Gateway Interface, helps Django serve our eventual web pages.
    iv) manage.py is used to execute various Django commands such as running the local web server or creating a new app.
    
9. Django comes with a built-in web server for local development purposes which we can start with the runserver command.
10. To run the manage.py run the command " python manage.py runserver ".
11. It will give you a localhost that directs to the Django welcome page.
12. If you find any errors annoying run the command " python manage.py migrate ".



# Creating an APP

1. To create the app run the command " python manage.py startapp pages ".
2. This creates a folder named pages and it also contains some files in that .
        1. admin.py is a configuration file for the built-in Django Admin app
        2. apps.py is a configuration file for the app itself
        3. migrations/ keeps track of any changes to our models.py file so our database and models.py stay in sync
        4. models.py is where we define our database models which Django automatically translates into database tables
        5. tests.py is for our app-specific tests
        6. views.py is where we handle the request/response logic for our web app
        
3. In your text editor, open the settings.py file and scroll down to INSTALLED_APPS where you’ll see six built-in Django apps already there. Add our new pages app (" 'pages.apps.PagesConfig' ")at the bottom
4. update the views.py file in our pages app as follows
         from django.http import HttpResponse
         def homePageView(request):
                return HttpResponse('Hello, World!')
5. Create a file " urls.py " in pages directory
6. Update it as follows
      from django.urls import path
      from .views import homePageView
      urlpatterns = [ path('', homePageView, name='home') ]
7. Now create another file "urls.py" in helloworld_project directory
8. Update it as follows
      from django.contrib import admin
      from django.urls import path, include 
      urlpatterns = [ path('admin/', admin.site.urls), path('', include('pages.urls')),]
9. Now the creation of app also completed.


# Now the helloworld app is created

# Now finally run again the command " python manage.py runserver " again it gives a url, copy the url and paste it on your browser , but now it will not direct to the Django welcome page , It will show the Hello World only.



## Thank You


