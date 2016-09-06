## Week Three Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What are the 3 main features in an ERD?  
Entities, their content and their relationships.  
2. Create an ERD for the following database: Restaurants, Customers, Items, Ingredients, Beverages, Orders, Vendors.  

3. What is the entry at the command line to create a new rails app?  
rails new <appname>  
4. What do Models generally inherit from in rails?  
ActiveRecord::Base  
5. What do Controllers generally inherit from in a rails project?  
ApplicationController  
6. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?  
resources :horse, only: [:show]  
7. What rake task is useful when looking at routes, and what information does it give you?  
rake routes tells you the HTTP Verb, the relative path, the controller and action which will handle the request and the prefix you can use as a shortcut for that route.  
8. What is an example of a route helper? When would you use them?  
ex: artist_path. These are a shorthand for an HTTP verb and a route. Use them anywhere you might otherwise use the full path, such as in links or redirects.  
9. What's the difference between what `_url` and `_path` return when combined with a routes prefix?  
`url` suffix gives you the full url, including the root. `path` gives you the relative path from the root.  
10. What are strong params and why are the necessary?  
Strong params use require and permit to select the right parameters for your active record object. They are necessary to prevent a form from posting data to fields it should not have access to, like users setting the admin flag to true by adding that to the form.  
11. What role does `form_for` play in helping us create our forms?  
`form_for` is a rails method that takes care of the basic features of a form for you. It makes sure you're using the correct HTTP verb and names all the form features for you.  
12. How does `form_for` know where to submit the user's input?  
The form is aware of the action used to reach it (new vs edit) and it finds the model matching the object given to it as an argument.  
13. Create a form using a `form_for` helper to create a new `Horse`.  
```
<%= form_for(@horse) do |f| %>
<%= f.label :name %>
<%= f.text_field :name %>
<%= f.label :birth_date %>
<%= f.date_field :birth_date %>
<%= f.submit %>
```
14. Why do we want to validate our models?  
The database is responsible for making sure the data it contains is accurate and valid. The model is the entry point of the database. Validations can check data as we insert it and alert us to problems or inconsistencies immediately.  
