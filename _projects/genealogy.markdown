---
layout: page
title: 🌱 Genealogy Database
description: >
  Created a data warehouse for online parish records from Lancashire, England. Processed the raw data using Python, stored the clean data in an SQLite3 database. Ruby on Rails for the CRUD and search functionality.

stack: Ruby on Rails, Python, SQLite3.
# demo: google.ca
# repo: google.ca
img: /assets/img/folk-finder.png
importance: 20
category: work
---

<iframe style="border:none" width="100%" height="450" src="https://whimsical.com/embed/TQXuAYRQrZyzNmTv38Hy9q"></iframe>

## **How it was built**

### 1. Scraping the web

Genealogical data often available in less than ideal format; however, I was fortunate enough to find the Lancashire Online Parish Clerks website, which contained baptism, marriage and death records.

I took advantage of the consistent HTML structure of the website to perform web scraping using Beautiful Soup 4, which is a Python library that helps you do this pretty easily. The difficulty of this task really depends on how easily you can find a pattern in the HTML structure of the web page you are looking to scrape.

I was able to extract the information, but the format of the resulting data left something to be desired...

### 2. Creating a database

I initially processed the raw data using Python, and stored the clean data in an SQLite3 database. The problems to sort out included: how is the date formatted? What is the gender of the individual and the relatives? Who are the mentioned relatives? What information can be derived from the provided attributes?

With all of these different components, it made sense to model data using an object-oriented approach. Once a record is parsed into the relevant components the data is handed to the relevant class constructor (birth, marriage, and death) to turn into usable objects. These record and person objects are then inserted into the database and will be searchable using the Find My Folks web app.

### 3. Building a web app

Having previously used Ruby on Rails at a hackathon, I decided this would be an excellent solution to build the CRUD functionality of the application. Ruby on Rails is well documented, it allows interaction with a database, and can be easily deployed using Heroku, allowing me to iterate more quickly.

The general user flow is that the user posts their query to the server using the search functionality, namely the person for which they want to find parish records. Then the server extracts all records from the database that are related to the requested person and returns the formatted information.

Genealogy is a personal hobby, so having lots of experience searching parish records myself, I knew that often the names of the individuals vary a lot. For example, “Thomas” could have been named “Joseph Thomas” in his baptism record, have used his nickname “Tom” in his wedding record, and be remembered as “Thomas” in his death record. That’s why I implemented an algorithm to return the proper results even if the names differed slightly between parish records, inspired from a [search engine project](/projects/search-engine/) I built for school.
