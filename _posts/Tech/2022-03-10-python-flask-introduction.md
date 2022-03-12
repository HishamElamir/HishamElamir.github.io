---
layout: post
title: (Flask Series) 01. Introduction
categories: Tech-Post Python Flask
description: An introduction to Python Flask
keywords: Python Flask Web Framework
---

![Flask Logo](/images/blog/flask.png])


In this part of the series, you will learn about the different parts of a Flask application. You will
also write and run the first Flask web application.


## Introdiction



## Initialization

All Flask applications must create an application instance. The web server passes all 
requests it receives from clients to this object for handling, using a protocol called 
Web Server Gateway Interface (WSGI, pronounced “wiz-ghee”), cool right 😎.
The application  instance is an object of class Flask, usually created as follows:

```python
from flask import Flask
app = Flask(__name__)

```

The only required argument to the Flask class constructor is the name of the main
module or package of the application. For most applications, Python’s `__name__` 
variable is the correct value for this argument.

  > What is the `__name__` 😵???
  > The `__name__` argument that is passed to the Flask application constructor is a source of confusion among new Flask developers.
  > Flask uses this argument to determine the location of the application, which in turn allows it to locate other files that are part of the application, such as images and templates.

Later in the series, you will get to know more complex ways to initialize a Flask application,
but this time, for a simple application, this is all that is needed.



## Routes and View Functions

Clients (web browsers) will send requests to the web server, which in turn sends
them to the Flask application instance. After this the Flask application instance
needs to know what code it needs to run for each URL requested,
so it keeps a mapping of URLs to Python functions. The association between a URL and the function that handles it is called a route.

Per each request you should get one code of the following list:
1. Informational responses (_100–199_)
2. Successful responses (_200–299_)
3. Redirection messages (_300–399_)
4. Client error responses (_400–499_)
5. Server error responses (_500–599_)


The most convenient way to define a route in a Flask application is through the
`@app.route` decorator exposed by the application instance. The following example
shows how a route is declared using this decorator:

```python
@app.route('/')
def index():
  return '<h1>Hello World!</h1>'
```

> Decorators are a standard feature of the Python language.
> A common use of decorators is to register methods as handler functions to be invoked when certain events occur.

The previous example registers method `index()` as the handler for the application’s
root URL. While the `@app.route` decorator is the preferred method to register view
methods, Flask also offers a more traditional way to set up the application routes
with the `app.add_url_rule()` method, which in its most basic form takes three arguments:
* The URL.
* The endpoint name.
* the view function.

The following example uses `app.add_url_rule()` to register an `index()` method that is equivalent to the one shown previously:

```python
def index():
 return '<h1>Hello World!</h1>'

app.add_url_rule('/', 'index', index)
```

Users Methods like `index()` that handle application URLs are called *view functions*.
If the application is deployed on a server associated with the `www.example.com` domain
name, then navigating to `http://www.example.com/` in your browser would trigger
`index()` to run on the server.

The return value of this view method is the response the client receives.
If the client is a web browser, this response is the document that is displayed to 
the user in the browser window. 
A response returned by a view function can be a simple string with HTML content, 
but it can also take more complex forms, as you will see later.


Embedding response strings with HTML code in Python source files leads 
to code that is difficult to maintain. 

The examples in this part of the series do it only to introduce the concept of responses. 
You will learn a better way to generate HTML responses in next parts of the series.


If you pay attention to how some URLs for services that you use every day are formed, 
you will notice that many have variable sections. 
For example, the URL for your Facebook profile page has the format 
`https://www.facebook.com/<your-name>`, 
which includes your username, making it different for each user. 
Flask supports these types of URLs using a special syntax in the `@app.route` decorator. 
The following example defines a route that has a dynamic component:

```python
@app.route('/user/<name>')
def user(name):
 return '<h1>Hello, {}!</h1>'.format(name)
```

The portion of the route URL enclosed in angle brackets is the dynamic part. 
Any URLs that match the static portions will be mapped to this route, 
and when the view function is invoked, the dynamic component will be passed as an argument. 

In the preceding example, 
the name argument is used to generate a response that includes a personalized greeting. 
The dynamic components in routes are strings by default but can also be of different types. 
For example, the route `/user/<int:id>` would match only URLs that have an integer 
in the id dynamic segment, such as `/user/123`.

Flask supports the following data types:
* `string`
* `int`
* `float`
* `path for routes`, where:
  > The path type is a special `string` type that can include _forward slashes_, unlike the string type.



## Putting All Together

In the previous sections you learned about the different parts of a Flask web application,
and now it is time to write your first one.

The following application script shown in code snippet below defines
an application instance and a single route and view function, as described earlier.

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
  return '<h1>Hello World!</h1>'
```

Will put the whole codes in the github repo for the series, 
just you can clone and play with the code as you want, 
and will make it much easier for you to learn and train you skills.



## Development Web Server

Flask applications include a development web server 
that can be started with the flask run command. 

This command looks for the name of the Python script that contains 
the application instance in the FLASK_APP environment variable.

To start the the application from the previous section, 
first make sure the virtual environment you created earlier is activated 
and has Flask installed in it. 

For Linux and macOS users, start the web server as follows:

```shell
(venv) $ export FLASK_APP=hello.py
(venv) $ flask run
```

and will get the output:
```
* Serving Flask app "hello"
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

For Microsoft Windows users, the only difference is in how 
the `FLASK_APP` environment variable is set:

```shell
(venv) $ set FLASK_APP=hello.py
(venv) $ flask run
```

and of course you will get:
```
 * Serving Flask app "hello"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

Once the server starts up, it goes into a loop that accepts requests and services them.
This loop continues until you stop the application by pressing `Ctrl+C`.

With the server running, open your web browser and type `http://localhost:5000/`
in the address bar.


If you type anything else after the base URL, the application will not know how to
handle it and will return an *error code* `404` to the browser—the familiar error that
you get when you navigate to a web page that does not exist.

The web server provided by Flask is intended to be used only for development and testing.
You will learn about production web servers in next parts of the series.


The Flask development web server can also be started programmatically
by invoking the `app.run()` method. As you can put the following snippet at the end of the file:

```python
if __name__ == '__main__':
  app.run()
```

While the flask run command makes this practice unnecessary,
the `app.run()` method can still be useful on certain occasions, such
as _unit testing_, as you will learn in next parts of the Flask series.


## What Now 🤔

This part of the series is ends here, but the series continues.
Stay tuned for the next part, if not uploaded yet 😅.
And if you have any feedback, you can send me on email or twitter.

See You Soon,
Hisham.