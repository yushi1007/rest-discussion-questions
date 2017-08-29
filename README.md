# REST Discussion Questions

Take 30 minutes with your table choose a *resource* that your server contains data about. A resource will be something like 'books', 'users', 'episodes', or 'characters', something that your users will be performing CRUD actions on.

1. Write out the 7 RESTful routes that correspond to the 4 CRUD actions.  Be sure to include the HTTP verb, the name of the route and the corresponding CRUD action.  

  * What SQL (if applicable) would be fired in the controller actions for each of the routes.
  * Why might it be important that routes and resources have a conventional structure?
  * Which routes would you `render` a view and for which would you `redirect to` another route? Why?

2. Let's say you have built a Sinatra app that is a blogging platform. You have a Post and an Author model and you have controllers and routes for the CRUD actions of each model. You sit down at your computer and visit www.youramazingsinatrablog.com/posts:

    * What kind of web request is this making? (i.e. is it a `GET`, `POST`, etc request?)
    * What controller action (i.e. which route in which controller) will recieve that web request?
    * What is the response that your Sinatra app will send back to the client, i.e. the browser?

3. You have the following form for a new blog post:

  ```html
  <form action="???" method="???">

    <label>Title</label>
    <input type="text" name="post[title]">

    <label>Author</label>
    <input type="text" name="post[author]">

    <label>Content</label>
    <input type="text" name="post[content]">

    <input type="submit">

  </form>
  ```

 * What action and what method should the form be defined to have?
 * Given the correct action and method, what controller action will this form submit the form data to?
 * Draw out the params that would be created by submitting this form?
 * Bonus: Currently, form is structured such that the author field is a simple text field, and the user will have to input the name of an existing author. Can you change the form so that it offers a drop down menu of all of the existing author's from the database? What would the resulting params look like? How would you use these params to make a new post and associate it to the selected author?

4. Spend a few minutes mapping out a domain model for a parking lot. How would you model the relationship between cars and spaces? How would you keep track of how long a car had been parked in a space? How would you keep track of how much money someone would need to pay for having parked a certain amount of time?
