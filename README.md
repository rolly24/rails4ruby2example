## Paperclip Demo

### Reference Application

A simple rails4 app using ruby 2.0.0 for testing deployments on anyines.com .

### Install Codebase

Clone the git repository

    $ git clone git@github.com:anynines/rails4ruby2example.git
    $ cd rails4ruby2example
    $ bundle

Create database and run migrations

    $ rake db:create db:migrate

Run the rails server

    $ rails s

### View Application

From a web browser access the site via [localhost:3000](http://localhost:3000)

## Deploy the application to Anynines

Install the a9s gem

    $ gem install a9s

Edit the deployment manifest

    $ cp manifest.yml.example manifest.yml
    $ vim manifest.yml -> exchange all occurences of your_app_name with your desired application identifier

The https://github.com/cloudfoundry/heroku-buildpack-ruby.git buildpack is referenced within the provided manifest.yml.example . This buildpack is needed to support rails4 and ruby2.

Deploy the application 

    $ cf push

## Test suite

RSpec and Capybara used for Integration and Unit tests

    $ rspec