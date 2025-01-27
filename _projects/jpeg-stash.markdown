---
layout: page
title: 📷 JPEG Stash
description: >
  Built an image repository for users to stash all their best JPEGs. Supports user account creation and image uploads. Supported by a test suite built with Capybara and Selenium on github actions. Live demo deployed to Heroku.
stack: Ruby on Rails, Postgres, Amazon S3, Heroku.
demo: https://jpeg-stash.herokuapp.com
repo: https://github.com/aethelind/jpeg-stash
img: /assets/img/jpeg-stash.png
importance: 25
category: work
---

### [ → ⚡️ Source Code Here! ⚡️ ← ](https://github.com/aethelind/jpeg-stash)

![Tests](https://github.com/aethelind/jpeg-stash/actions/workflows/main.yml/badge.svg?branch=master) ![Heroku](https://pyheroku-badge.herokuapp.com/?app=jpeg-stash)

JPEG Stash is an [image repository](https://docs.google.com/document/d/1eg3sJTOwtyFhDopKedRD6142CFkDfWp1QvRKXNTPIOc/edit?usp=sharing) where users can stash + share all their best jpegs!  
Built with Ruby on Rails. Deployed on Heroku.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <a href="https://jpeg-stash.herokuapp.com/">
            <img class="img-fluid rounded" src="{{ '/assets/img/jpeg-stash-demo.png' | relative_url }}" alt="" title="Data staging plan."/>
        </a>
    </div>
</div>


## Demo

### [ → 🚀 Live Demo Here! 🚀 ← ](https://jpeg-stash.herokuapp.com/)

## Features

### 🏠 Feed

The main page of JPEG Stash shows a feed of all the images users have uploaded, with the most recent image on top.

### 🖼️ Image Upload

Users can upload images to JPEG stash. The image must be a JPEG or PNG, and have a maximum size of 3MB.  
Since JPEG Stash is deployed on Heroku (which has ephemeral storage), images must be stored elsewhere. I chose to integrate an Amazon S3 bucket for the image storage, and a Postgres database for everything else.

### 👥 User Access Management

JPEG Stash can be accessed without an account, but creating an account is quick and easy. I implemented simple authentication using bcrypt to encrypt passwords. When a user successfully logs in, a session is created. Logging out destroys this session. Images can only be editted or deleted if the logged in user is also the uploader of the image. Users can be created or deleted, and deleting a user also deletes any images they uploaded.

### Further Features

Here are some possible features which could be implemented in the future.

- ❤️ **Interaction**: Allow users to comment on each other's images, or react with emojis
- 🏷 **Tagging**: Allow users to add tags to their uploaded images to #categorize and #group images under similar #themes
- 🔎 **Search**: Explore all the uploaded images by searching for keywords or tags
- 👀 **Authorization**: Allow users to choose who can see their images. Currently, all images have a 'public' scope. Allow images to be 'private' (only visible to the uploader), 'unlisted' (public only to those with a link), or 'custom' (uploader specifies which users may view)
- 🔐 **Security**: If this app were to go to production, the security would need to be improved. I would likely implement [Devise](https://github.com/heartcombo/devise) (or similar) as a more robust authentication solution.

## Test Suite

![Tests](https://github.com/aethelind/jpeg-stash/actions/workflows/main.yml/badge.svg?branch=master)  
The test suite was created with Capybara, Selenium, and RSpec. They test the functionality of user creation / deletion, and image upload, editting, and deletion. I created [a github action](https://github.com/aethelind/jpeg-stash/actions/workflows/main.yml) to run the tests after every commit or pull request. The change won't be deployed to Heroku unless all the tests pass.

The tests can be run locally with the following command:

```bash
HEADLESS=true bundle exec rspec spec/features
# OR
bundle exec rspec spec/features
```

## Local Setup

Clone this repo, and cd into the jpeg-stash folder.

```bash
git clone https://github.com/aethelind/jpeg-stash.git
# OR
git clone git@github.com:aethelind/jpeg-stash.git
```

```bash
cd jpeg-stash
```

Ensure all the required dependencies are installed:

```bash
bundle install
```

Run the Database Migrations:

```bash
rake db:migrate
```

Serve jpeg-stash:

```bash
rails s
```

jpeg-stash should now be running [locally on port 3000](http://localhost:3000/)!
