# Laravel With Vue/Vueitfy Single Page Application Boilerplate

## About

This is a boilerplate project for applications using a Laravel Backend with a Single Page Application using VueJS and Vuetify. I decided to make this boilerplate after wrestling with this setup for some time.

### Assumptions
This project assumes the user has a base knowledge of Laravel and VueJS, documentation can be found here:
* [Laravel](https://laravel.com/)
* [VueJS](https://vuejs.org/)

The styling for the frontend is done using [Vuetify](https://vuetifyjs.com/), exploring this documentation will help you understand the components and tags used in the frontend.

## Installation
Assuming you have PHP, MySQL, and a Web Server installed (or you are using a Vagrant machine like Laravel's [Homestead](https://laravel.com/docs/5.5/homestead)) to get this project running simply:

`git clone https://github.com/aturingmachine/laravel-vue-spa-boilerplate.git <directory name>`

`cd <directory name>`

If you are using a VM the following commands can be executed from the proper directory in the VM

Then:

Make our own `.env`:

&nbsp;&nbsp;&nbsp;&nbsp;`cp .env.example .env` 





Install all our dependencies:

&nbsp;&nbsp;&nbsp;&nbsp;`npm install`

&nbsp;&nbsp;&nbsp;&nbsp;`composer install`

Generate a Key for the application:

&nbsp;&nbsp;&nbsp;&nbsp;`php artisan key:generate`

Build the Javascript

&nbsp;&nbsp;&nbsp;&nbsp;`npm run dev` _This should be done after any changes to the Vue application_

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; _alternatively_ 

&nbsp;&nbsp;&nbsp;&nbsp;`npm run watch` _This will watch for changes made to the JS section of the build_

Then navigate to wherever the application lives and you should see the Vue Application.

## Project Structure

### Frontend

`/resources/`

  &nbsp;&nbsp;`/assets/js/` Here lives all of your JavaScript for the Front End of the application

  &nbsp;&nbsp;&nbsp;&nbsp;`/components/` Here is where we will place new Vue Components, an example is already there for you.

  &nbsp;&nbsp;&nbsp;&nbsp;`/config/` Any config .js files you need, a base [Axios](https://github.com/axios/axios) config is here already. You can create more Axios configs &nbsp;&nbsp;&nbsp;&nbsp;simply by following the same conventions laid out in this file. 

  &nbsp;&nbsp;&nbsp;&nbsp;`/router/` The `index.js` of this directory is used to set all routes and rules for the `vue-router` we use.

  &nbsp;&nbsp;&nbsp;&nbsp;`/stylus/` The Vuetify styling is in here, we need not worry about it.
    
  &nbsp;&nbsp;&nbsp;&nbsp;`/app.js` This is the main driver of the frontend application, unless you are adding new node modules to it, this &nbsp;&nbsp;&nbsp;&nbsp;should work out of the box.
    
  &nbsp;&nbsp;&nbsp;&nbsp;`/App.vue` This is the main Vue component. It is a toolbar, nav-drawer, and footer with a router view in the middle &nbsp;&nbsp;&nbsp;&nbsp;where other components are displayed.
  
  &nbsp;&nbsp;`/views/app.blade.php` This is a simple file that has our Vue application dropped into it.

### Backend

The backend of this project follows the same conventions of Laravel. I suggest looking into their documentation and familiarizing yourself with the `php artisan` commands. They are used to create everything you need including **Models, Migrations, and Controllers**.

### Dependencies 

Some Dependencies in this application that may differ from a base VueJS install or Laravel install include:

1. NPM
* [vue-cookie](https://github.com/alfhen/vue-cookie) To help manipulate cookies on the frontend
* [vue-router](https://github.com/vuejs/vue-router) To route views with the SPA

2. Composer
* [barrvdh/cors](https://github.com/barryvdh/laravel-cors) To enable CORS on the server side if needed (This is on by default, to disable it just follow the documentation)
