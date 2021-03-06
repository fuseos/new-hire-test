# FuseOS Demo Project

## Setup

Use this guide to setup your development environment.  This project uses a vm to host
itself in and vagrant to manage the machine.  

You will need to install several supporting applications before you can start your environment.

You will need

- a VM host (Virtalbox, VMware, parallels)
    - Download your preferred vm host ([Virtualbox](https://www.virtualbox.org/wiki/Downloads) is preferred)
- Vagrant management client
    - [download](https://www.vagrantup.com/downloads.html) 
- NodeJS
    - [download](https://nodejs.org/en/download/current/)
    
1. Once you have downloaded and installed the supporting applications you can start your 
development environment using the command `vagrant up` from the project root

2. you will need to edit your hosts file and add the local entry `192.168.33.10 vagrant.local`

3. You will then need to install and build your node dependencies with `npm install`

4. You can then build the javascript for the app `npm run development`

5. Your app should be up and running and accessible from [http://vagrant.local](http://vagrant.local)

6. profit

## Expanded Help

### Vagrant commands

`vagrant up`
Brings up your development environment

`vagrant halt`
Stops your environment without destroying persistent data

`vagrant destroy`
Destroys your development environment. A new rebuild will be required when starting your environment again.

`vagrant provision`
Force a re-run the vagrant provisioning script.  The script will skip any

`vagrant ssh`
ssh into your development environment 

### bash commands

There are shell commands within the vagrant environment to help you with common tasks

`run_mode` resets the app back to development run mode

`test_mode` sets the app to run in test mode 

`run_lint` runs the complete code lint

`run_unit_tests`  run all of the unit tests

## Directory Descriptions

`/App`

This is the main app source folder.  All php source files are found in this folder. The core of the
application is in `library/App.php`

`/App/Views`

This is where all of the view templates are stored.


`/App/Models`

All models are stored here. All models must extend base `App\Model`

`/migrations`

Database migrations are stored here. See the migrations section for more information on 
database migrations

`/src/js`

All javascript source is kept here.

## Database Migrations

Database migrations use the phinx library.  You can find all of the usage documentation
[here](http://docs.phinx.org/en/latest/migrations.html).

to create a migration
1. ssh into your development environment `vagrant ssh`
2. cd into your project folder `cd Code`
3. create the migration `./vendor/bin/phinx create [MyAmazingMigrationName]`
4. find your new migration in the `/migrations` folder
5. When you are ready to run your migration `./vendor/bin/phinx migrate`
6. (optional) if you need to roll your migration back`./vendor/bin/phinx rollback`

## PHP

This project uses php version 7.3. All of the documentation is available here [https://www.php.net/docs.php](https://www.php.net/docs.php)

*Slim PHP* is the framework used.  You can find specific documentation here [http://www.slimframework.com/docs/v3/](http://www.slimframework.com/docs/v3/)

*Eloquent ORM* is used for the model layer. Documentation can be found [here](https://laravel.com/docs/5.0/eloquent) on it's use

## Javascript

this project uses vue.js as it's framework. you can find the development
documentation [here](https://vuejs.org/v2/guide/).

### commands

`npm run development`  Build the application in development mode

`npm run watch`  Build the application in development mode and watch for file changes

`npm run production` Build the application in production mode.  Development tools are unavailable.

## CSS/FontAwesome

Styles are found in `src/scss/styles.scss`.  Any changes to this file will require
you to rebuild using `npm run development` or `npm run watch`

### Vuetify
This project uses a component based css framework called vuetify.  You can
find all of the component documentation [here](https://vuetifyjs.com/en/components/api-explorer)

Icons are provided through fontawesome.  You can see the complete icon set at [https://fontawesome.com/icons](https://fontawesome.com/icons)

## Tasks

The overall purpose of this sample application will be to create a company contacts list.

The application will be able to
- Store multiple companies.
- Store multiple contacts for each company.

### Steps
1. Replace the index page header with an appropriate application welcome banner.

2. Add a web form that will allow the user to add a new company.
    - form should include an input for company name
    
3. Add an endpoint to save the new company to the database

4. Add a delete button to the company list ui

5. Add endpoint to delete company

6. Add a migration that will create a contact as a child of the company model
    - Add a new contact model
        - contact model will have columns (name, phone, email)

7. Add a form that will allow the user to add a contact to the company

8. Add an endpoint that will save the contacts to the database

9. Add delete button to company contact

10. Add delete endpoint for company contact

11. (Extra Credit)  Add search feature to company list

### Check In Process
To return your code back to use create your own github repo.  Follow the instructions to add your remote to the git repository.  Branching is not required and you can make all of your commits to master.  Please try and retain all of your commit history and comments as appropriate.

Send us the link to your git repo when you are finished.

Ask as many questions you need if you run into trouble. 
