---
layout: post
title: (Flask Series) 02. Simple App Continues
categories: Tech-Post Python Flask
description: An introduction to Python Flask
keywords: Python Flask Web Framework
---

![Flask Logo](/images/blog/flask.png)


In this part of the series, you will learn about the different parts of a Flask application. You will
also write and run the first Flask web application.


## Introdiction

Flask is a small framework by most standards—small enough to be called a “microframework,” 
and small enough that once you become familiar with it, you will likely
be able to read and understand all of its source code.

But being small does not mean that it does less than other frameworks. 
Flask was designed as an extensible framework from the ground up; 
it provides a solid core with the basic services, while extensions provide the rest. 
Because you can pick and choose the extension packages that you want, 
you end up with a lean stack that has no bloat and does exactly what you need.

And in this series, we will go from the basics of how to install and work with flask, 
to building applications that serve some purposes. 
Stay tuned for the next parts of the series and hope that will get interesting through time 😋.

Let's continue with the next thing in our list 🥳.



## Building Configurations


The first thing that comes to mind is configuring a Flask application as per the need. In this
recipe, we will try to understand the different ways in which Flask configurations can be done.

Getting ready
In Flask, a configuration is done on an attribute named **config** of the Flask object.
The **config** attribute is a subclass of the dictionary data type, and we can modify it
just like any dictionary.

For instance, to run our application in the debug mode, we can write the following:
    ```python
        app = Flask(__name__)
        app.config['DEBUG'] = True
    ```

The debug **Boolean** can also be set at the Flask object level rather than at the config level:
    ```python
        app.debug = True
    ```

Alternatively, we can use this line of code:
    ```python
        app.run(debug=True)
    ```

Enabling the debug mode will make the server reload itself in the case
of any code changes, and it also provides the very helpful Werkzeug
debugger when something goes wrong.
There are a bunch of configuration values provided by Flask. We will come across them in the
relevant recipes.

As the application grows larger, there originates a need to manage the application's configuration in a separate file as shown here. Being specific to machine-based setups in most cases will most probably not be a part of the version-control system. For this, Flask provides us with multiple ways to fetch configurations. The most frequently used ones are discussed here:
* From a Python configuration file (`*.cfg`), the configuration can be fetched using:
    `app.config.from_pyfile('myconfig.cfg')`
* From an object, the configuration can be fetched using:
    `app.config.from_object('myapplication.default_settings')`
    Alternatively, we can also use:
    `app.config.from_object(__name__)   # To load from same file`
* From the environment variable, the configuration can be fetched using:
    `app.config.from_envvar('PATH_TO_CONFIG_FILE')`


How it works…
Flask is intelligent enough to pick up only those configuration variables that are written in
uppercase. This allows us to define any local variables in our configuration files/objects and
leave the rest to Flask.
The best practice to use configurations is to have a bunch of default
settings in app.py or via any object in our application itself and then
override the same by loading it from the configuration file. So, the code
will look like this:

    ```python
        app = Flask(__name__)
        DEBUG = True
        TESTING = True
        app.config.from_object(__name__)
        app.config.from_pyfile('/path/to/config/file')
    ```


## Class-based settings

An interesting way of laying out configurations for different deployment modes, such as
production, testing, staging, and so on, can be cleanly done using the inheritance pattern
of classes. As the project gets bigger, you can have different deployment modes such as development, staging, production, and so on, where each mode can have several different configuration settings, and some settings will remain the same.


How to do it…
We can have a default setting base class, and other classes can inherit this base class and override or add deployment-specific configuration variables.

The following is an example of our default setting base class:

    ```python
        class BaseConfig(object):
            """Base config class"""
            SECRET_KEY = 'A random secret key'
            DEBUG = True
            TESTING = False
            NEW_CONFIG_VARIABLE = 'my value'
        
        class ProductionConfig(BaseConfig):
            """Production specific config"""
            DEBUG = False
            SECRET_KEY = open('/path/to/secret/file').read()
    
        class StagingConfig(BaseConfig):
            """Staging specific config"""
            DEBUG = True
    
        class DevelopmentConfig(BaseConfig):
            """Development environment specific config"""
            DEBUG = True
            TESTING = True
            SECRET_KEY = 'Another random secret key'
    ```

The secret key is stored in a separate file because, for security concerns, it should not be a part of your version-control system.
This should be kept in the local filesystem on the machine itself, whether it is your personal machine or a server.

How it works…
Now, we can use any of the preceding classes while loading the application's configuration via `from_object()`. Let's say that we save the preceding class-based configuration in a file named `configuration.py`:

    ```python
        app.config.from_object('configuration.DevelopmentConfig')
    ```

So, overall, this makes the management of configurations for different deployment
environments flexible and easier.




## What Now 🤔

This part of the series is ends here, but the series continues.
Stay tuned for the next part, if not uploaded yet 😅.
And if you have any feedback, you can send me on email or twitter.

See You Soon,
Hisham.