
# Using APIs with Python

### Introduction to REST API parsing with python!

API stands for Application Programming Interface and are essentially a way to access a piece of information from a website or service. REST stands for representational state transfer which is a way of describing how APIs should look and work. In most cases, especially for web APIs, a REST interface is generally a URL that you can click to get some information from the website.

We'll be using Python to make use of some web APIs! Lets get started!


## Prerequisites

In order to get started, we need Python version 2.7 or higher and access to the internet. We also need some basic knowledge of python: things like defining a function and how lists and strings work

## Introduction

We will be using a website called firebase to get data for some of our APIs. This website has a collection of some public datasets: like weather and bus routes. We will also be using the google maps images api

## JSON

### Understanding JSON

JSON is a format for representing data. It is a very common thing that a lot of APIs use. JSON essentially looks like this. Everything is inside `{}` and you have multiple entires which contan keys and values

```json
{
  "key_name" : "value",
  "numeric_key" : 42,
  "list_items" : [1, 2, "three", "four"],
  "dictionary" : { "another_key" : "another value" }
}
```

### Reading JSON

We are going to use these simple tricks

- If it is a **number**, its a **number**!
- If it is inside **double quotes**, it is a **string**
- If it has **square brackets**, it is a **list**!
- If it has **curly braces**, it is a **dictionary**

## Reading the Weather

### Opening the website in python

```py
import json
import urllib2

# This is the API URL
api = "https://publicdata-weather.firebaseio.com/sanfrancisco/currently.json"

get = urllib2.urlopen(api).read()

print get
```

**This gives us something like:**

![](https://camo.githubusercontent.com/92500dcee84fac0a563104ed2ee62df2ae9e099b/687474703a2f2f692e696d6775722e636f6d2f4a5553354945622e706e67)

### Parsing JSON in python

```py
import json
import urllib2

api = "https://publicdata-weather.firebaseio.com/sanfrancisco/currently.json"
get = urllib2.urlopen(api).read()
data = json.loads(get)

print data
```

**This gives us something like:**

![](https://cloud.githubusercontent.com/assets/461702/2912224/74e236a2-d673-11e3-866f-63355c0c44b9.JPG)




### Writing a function to return our data

```py
import json
import urllib2

def get_data(api):
  get = urllib2.urlopen(api).read()
  data = json.loads(get)

  return data
  
api = "https://publicdata-weather.firebaseio.com/sanfrancisco/currently.json"
data = get_data(api)

print data
```

### Reading JSON in Python

Reading is simple. We just need to define the key name and we get back it's value!

```py
print data['temperature'] #=> 52.46
prnt data['summary'] #=> "Partly Cloudy"
```

#### Tasks

- **Lets print a few more properties**
- **Print the temperature in Celsius**
  - Use the formula:  `(temperature -32) * 5.0/9.0`

## Checking MUNI Status

```py
```

## Lets add Maps!

```py
```

## Homework

- Add more than 1 location on the map
