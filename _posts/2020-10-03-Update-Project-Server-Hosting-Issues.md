---
layout: post
title:  "Industrial Project Update - Server Hosting Bug Fix"
date:   2020-03-10
categories: jekyll update
---
## Server Hosting issues
I had a few problems when running the server on localhost with port number 5000, when I make a GET request from my react website to http://127.0.0.1:5000/messages/, my react website was unable to access the API requests it because both the Flask and NPM servers were running on localhost (127.0.0.1) but with different port numbers.

The error I was particularly getting was
Access to fetch at 'http://127.0.0.1:5000/messages/' from origin 'http://localhost:3000' has been blocked by CORS policy.

However, to solve this issue I installed the Flask-CORS extension so that I could get access to the requests made by my react website. I changed some code on the api.py so that I could fix that error is that okay? Or there could be a workaround to this ?

This is how I fixed the issue:  
1) install the dependencies
    (pip3 install -U flask-cors)

2) in Api.py  
from flask import Flask  
from flask_cors import CORS  
app = Flask(name)  
CORS(app)
