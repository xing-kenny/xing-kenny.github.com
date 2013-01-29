<h2><font size="16" color="blue">ember-data-example startup</font></h2>
## 0.  git it

git@github.com:dgeb/ember_data_example.git

## 1.  rails s

在应用root目录下，执行rails s，rails 版本是3.2.9。触发script/rails


	#!/usr/bin/env ruby
	# This command will automatically be run when you run "rails" with Rails 3 gems installed from the root of your application.

	APP_PATH = File.expand_path('../../config/application',  __FILE__)
	require File.expand_path('../../config/boot',  __FILE__)
	require 'rails/commands'

## 2.  config/boot.rb

	require 'rubygems'

    # Set up gems listed in the Gemfile.
    ENV['BUNDLE_GEMFILE'] ||= File.expand_path('../../Gemfile', __FILE__)

    require 'bundler/setup' if File.exists?(ENV['BUNDLE_GEMFILE'])    

setup Gemfile    

## 3.  rails/commands.rb

经过复杂的过程，调用到config.ru

## 4.  config.ru

	# This file is used by Rack-based servers to start the application.

	require ::File.expand_path('../config/environment',  __FILE__)
	run EmberDataExample::Application

## 5. config/environment.rb

	# Load the rails application
	require File.expand_path('../application', __FILE__)

	# Initialize the rails application
	EmberDataExample::Application.initialize!

## 6. config/application.rb

	require File.expand_path('../boot', __FILE__)

	require 'rails/all'
	...
	module EmberDataExample
		class Application < Rails::Application


## 7. config/routes.rb

	EmberDataExample::Application.routes.draw do
	  scope ":api" do
	    resources :contacts
	  end
	  root :to => 'contacts#index101'
	  match "/*path" => "contacts#index"
	end


At the core of Rails is the Model, View, Controller architecture, usually just called MVC.
The 'root :to =>' tells Rails to map the root action to the controller’s index action.

## 8. application.html.erb
This is current default template.

	<!DOCTYPE html>
	<html>
	<head>
	  <title>EmberDataExample</title>
	  <%= stylesheet_link_tag    "application" %>
	  <%= javascript_include_tag "application" %>
	  <%= csrf_meta_tags %>
	</head>
	<body>
	<%= yield %>
	</body>
	</html>

stylesheet_link_tag gets css assets/stylesheets/application.scss
javascript_include_tag gets js assets/javascripts/application.js

application.js load all project's js.

## 9. go to ember
in asset/javascripts/app.js

	App = Em.Application.create();

ember should have the content from assets/javascripts/templates/application.hbs

## more: add ember to rails project

###1. add to Gemfile.
	gem 'ember-rails', github: 'emberjs/ember-rails'
###2 >bundle install
###3 >rails g ember:bootstrap
result:

      insert  app/assets/javascripts/application.js
      create  app/assets/javascripts/models
      create  app/assets/javascripts/models/.gitkeep
      create  app/assets/javascripts/controllers
      create  app/assets/javascripts/controllers/.gitkeep
      create  app/assets/javascripts/views
      create  app/assets/javascripts/views/.gitkeep
      create  app/assets/javascripts/routes
      create  app/assets/javascripts/routes/.gitkeep
      create  app/assets/javascripts/helpers
      create  app/assets/javascripts/helpers/.gitkeep
      create  app/assets/javascripts/templates
      create  app/assets/javascripts/templates/.gitkeep
      create  app/assets/javascripts/myapp.js
      create  app/assets/javascripts/router.js
      create  app/assets/javascripts/store.js
      create  app/assets/javascripts/views/application_view.js
      create  app/assets/javascripts/templates/application.handlebars
      create  app/assets/javascripts/controllers/application_controller.js
      create  app/assets/javascripts/routes/application_route.js

add to application.js
	+//= require handlebars
	+//= require ember
	+//= require ember-data
	+//= require_self
	+//= require myapp
	+Myapp = Ember.Application.create({
	+});

###3 add to config/environments/development.rb

	config.ember.variant = :development

## reference
[rails初始化流程(一)]   
[rails初始化流程(二)]    
[rails初始化流程(三)]    
[How to use Ember.js with Rails]    
[Getting Started with Rails]    

[rails初始化流程(一)]: http://kenbeit.com/posts/110/rails%E5%88%9D%E5%A7%8B%E5%8C%96%E6%B5%81%E7%A8%8B(%E4%B8%80)
[rails初始化流程(二)]: http://kenbeit.com/posts/111/rails%E5%88%9D%E5%A7%8B%E5%8C%96%E6%B5%81%E7%A8%8B(%E4%BA%8C)
[rails初始化流程(三)]: http://kenbeit.com/posts/113/rails%E5%88%9D%E5%A7%8B%E5%8C%96%E6%B5%81%E7%A8%8B(%E4%B8%89) 
[How to use Ember.js with Rails]: http://www.pansapien.com/2013/01/16/how-to-use-ember-js-with-rails
[Getting Started with Rails]: http://guides.rubyonrails.org/getting_started.html