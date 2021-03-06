---
title: API Reference

language_tabs:
  - ruby
  - javascript

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - config_options

search: true
---

# Introduction

Wrenchmode is the fastest, easiest way to create a beautiful "Down For Maintenance" page for your web app. Following these basic instructions, you will have your Wrenchmode project set up in less than 5 minutes.

# Installation As A Heroku Addon

```ruby
# Install the Heroku Addon via the CLI
heroku addons:create wrenchmode:test

# In your Gemfile
gem 'wrenchmode-rack' 

# For Ruby on Rails, add this to /config/environments/production.rb
config.middleware.insert_before 0, Wrenchmode::Rack

# For a Rack application, add this to your-rack-app.rb
require 'rubygems' 
require 'bundler/setup' 
Bundler.require(:default) 
use Wrenchmode::Rack
```

```javascript
// Install the Heroku Addon via the CLI
heroku addons:create wrenchmode:test

// Install the npm package
npm install wrenchmode-express

// In your app.js 
var express = require('express');
var app = express();
var wrenchmodeExpress = require('wrenchmode-express');
 
app.use(wrenchmodeExpress());
```

(Be patient with any issues, we're still in the submission process with our Addon)

Add the Wrenchmode Addon via the Heroku CLI. Then install the middleware layer. For Ruby/Rack, this means a Rubygem. For NodeJS/Express, this means an npm package. Finally, make sure to include the middleware layer in your application.

Once everything is installed, you can go to your Heroku dashboard and click on the Wrenchmode link to log into your Wrenchmode dashboard. From there you can turn Wrenchmode on and off for your project.

# Manual Installation (non-Heroku)

```ruby
# In your Gemfile
gem 'wrenchmode-rack' 

# For Ruby on Rails, add this to /config/environments/production.rb
config.middleware.insert_before 0, Wrenchmode::Rack, jwt: "copy-and-paste-the-JWT-from-your-project-page-it-will-be-long!"

# For a Rack application, add this to your-rack-app.rb
require 'rubygems' 
require 'bundler/setup' 
Bundler.require(:default) 
use Wrenchmode::Rack, jwt: "copy-and-paste-the-JWT-from-your-project-page-it-will-be-long!"
```

```javascript
// Install the npm package
npm install wrenchmode-express

// In your app.js 
var express = require('express');
var app = express();
var wrenchmodeExpress = require('wrenchmode-express');
 
app.use(wrenchmodeExpress({
  jwt: "your-really-long-jwt"
}));
```

Install the middleware layer. For Ruby/Rack, this means a Rubygem. For NodeJS/Express, this means an npm package. Include the middleware layer in your application and configure it with your JWT, which can be found on your project page in the Wrenchmode dashboard.
