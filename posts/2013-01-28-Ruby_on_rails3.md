Ruby on rails3
========================

### Create web project framework

E:\temp>rails new myapp
NOTE: here need run gem install times for some compnents.
E:\temp>cd myapp
E:\temp\myapp>rails server
	...
	[2013-01-28 11:38:16] INFO  WEBrick::HTTPServer#start: pid=10212 port=3000

Access 'http://localhost:3000/', there will display a web page 'public/index.html'.

E:\temp\myapp>rake routes


E:\temp\myapp>

rake routes is null since the routes.rb is null now.

### Create controller && view

create helloworld_controller.rb

	class HelloworldController < ApplicationController
		def say
		end
	end

create new folder 'helloworld', create file 'say.html.erb' under this forder.

	hello world!

update routes.rb with

	Myapp::Application.routes.draw do
	   match ':controller(/:action(/:id(.:format)))'
	end

access 'http://localhost:3000/helloworld/say' is OK.


E:\temp\myapp>rake routes
  /:controller(/:action(/:id(.:format))) :controller#:action

E:\temp\myapp>

### Resource route rule

#### root
	root :to => 'pages#main'    

* put the root route at the top of the file, because it is the most popular route and should be matched first.
* need to delete the public/index.html file for the root route to take effect.



#### resources
resources :photos

creates seven different routes in your application, all mapping to the Photos controller:

HTTP Verb|      Path    |   action  |   used for    
GET        /photos          index      display a list of all photos     
GET        /photos/new      new        return an HTML form for creating a new photo     
POST       /photos          create     create a new photo    
GET        /photos/:id      show       display a specific photo     
GET        /photos/:id/     edit       edit	return an HTML form for editing a photo    
PUT        /photos/:id      update     update a specific photo   
DELETE     /photos/:id      destroy    delete a specific photo    

### Exercise
E:\temp\myapp>rails generate scaffold contact name:string mail:string
result:  

* add 'resources :contacts' to routes.rb
* generate files 'views/contacts/*'
* generate file contacts_controller.rb
* generate file contact.rb
* genarate file contacts_helper.rb
* genarate file 'db/migrate/20130128063625_create_contacts.rb'

E:\temp\myapp\db\migrate>rake db:migrate    
(in E:/temp/myapp)    
==  CreateContacts: migrating =================================================    
-- create_table(:contacts)    
   -> 0.0030s    
==  CreateContacts: migrated (0.0030s) ========================================   

Now can access 'http://localhost:3000/contacts/new'.

Amend routes.rb to

	  root :to => 'helloworld#say'
	  resources :contacts
	  scope ":ccc" do
	    resources :contacts
	  end
	  scope :module => "admin" do
	    resources :posts
	  end

'http://localhost:3000/ccc/contacts/new' and 'http://localhost:3000/contacts/new' go to same point.


	E:\temp\myapp\db\migrate>rake routes
	(in E:/temp/myapp)
	        root        /                                 helloworld#say
	    contacts GET    /contacts(.:format)               contacts#index
	             POST   /contacts(.:format)               contacts#create
	 new_contact GET    /contacts/new(.:format)           contacts#new
	edit_contact GET    /contacts/:id/edit(.:format)      contacts#edit
	     contact GET    /contacts/:id(.:format)           contacts#show
	             PUT    /contacts/:id(.:format)           contacts#update
	             DELETE /contacts/:id(.:format)           contacts#destroy
	             GET    /:ccc/contacts(.:format)          contacts#index
	             POST   /:ccc/contacts(.:format)          contacts#create
	             GET    /:ccc/contacts/new(.:format)      contacts#new
	             GET    /:ccc/contacts/:id/edit(.:format) contacts#edit
	             GET    /:ccc/contacts/:id(.:format)      contacts#show
	             PUT    /:ccc/contacts/:id(.:format)      contacts#update
	             DELETE /:ccc/contacts/:id(.:format)      contacts#destroy
	       posts GET    /posts(.:format)                  admin/posts#index
	             POST   /posts(.:format)                  admin/posts#create
	    new_post GET    /posts/new(.:format)              admin/posts#new
	   edit_post GET    /posts/:id/edit(.:format)         admin/posts#edit
	        post GET    /posts/:id(.:format)              admin/posts#show
	             PUT    /posts/:id(.:format)              admin/posts#update
	             DELETE /posts/:id(.:format)              admin/posts#destroy


### Reference
[Ruby on rails3新手谈(2):简单的例子helloworld]    
[深入浅出说路由]    
[Rails Routing from the Outside In]    


[Ruby on rails3新手谈(2):简单的例子helloworld]: http://www.cnblogs.com/newmin/archive/2010/10/10/ruby_on_rails_3_start_02.html    
[深入浅出说路由]: http://guides.ruby-china.org/routing.html    
[Rails Routing from the Outside In]: http://guides.rubyonrails.org/routing.html   
