# REST Discussion Questions

Take 30 minutes with your table choose a *resource* that your server contains data about. A resource will be something like 'books', 'users', 'episodes', or 'characters', something that your users will be performing CRUD actions on.

1. Write out the 7 RESTful routes that correspond to the 4 CRUD actions.  Be sure to include the HTTP verb, the name of the route, the path (URL) and the corresponding CRUD action. 

   * What SQL (if applicable) would be fired in the controller actions for each of the routes?
   * Why might it be important that routes and resources have a conventional structure?
   * Which routes would you `render` a view and for which would you `redirect to` another route? Why?

2. Let's say you have built an app that is a blogging platform. You have a Post and an Author model and you have controllers and routes for the CRUD actions of each model. You sit down at your computer and visit www.youramazingsinatrablog.com/posts:

   * What kind of web request is this making? (i.e. is it a `GET`, `POST`, etc request?)
   * What controller action (i.e. which route in which controller) will recieve that web request?
   * What is the response that your Sinatra app will send back to the client, i.e. the browser?

4. Spend a few minutes mapping out a domain model for a parking lot. How would you model the relationship between cars and spaces? How would you keep track of how long a car had been parked in a space? How would you keep track of how much money someone would need to pay for having parked a certain amount of time?

 Group members: Jamie, Doug, Linda, Jeff P, Yu Shi,  Alex P,  Alex R and Marty W. We decided to stay in the lecture zoom and have a super DQ group
Write out the 7 RESTful routes that correspond to the 4 CRUD actions. Be sure to include the HTTP verb, the name of the route, the path (URL) and the corresponding CRUD action.
      - Route: #index, path: '/posts', HTTP verb: GET, CRUD: Read

      - Route: #new, path: '/posts/new', HTTP verb: GET, CRUD: Create

      - Route: #create, path: '/posts', HTTP verb: POST, CRUD: Create

     - Route: #show, path: '/posts/:id', HTTP verb: GET, CRUD: Read

     - Route: #edit, path: '/posts/:id/edit', HTTP verb: GET, CRUD: Update

     - Route: #update, path: '/posts/:id', HTTP verb: PATCH, CRUD: Update

     - Route: #destroy, path: '/posts/:id', HTTP verb: DELETE, CRUD: Destroy

What SQL (if applicable) would be fired in the controller actions for each of the routes? every HTTP request triggers an action in SQL, either to Index, New, Create, Show, Edit, Update or Destroy
Why might it be important that routes and resources have a conventional structure?  
     - Because it is easier to work with and maintain code written by different devs and teams.

Which routes would you render a view and for which would you redirect to another route? Why? 
     - Render: all the GET requests

     - Redirect: POST, PATCH, DELETE requests

Let's say you have built an app that is a blogging platform. You have a Post and an Author model and you have controllers and routes for the CRUD actions of each model. You sit down at your computer and visit www.youramazingsinatrablog.com/posts
What kind of web request is this making? (i.e. is it a GET, POST, etc request?) Everything comes from the browser bar is a GET request
What controller action (i.e. which route in which controller) will recieve that web request? /posts route,  to: posts#routes
What is the response that your Sinatra app will send back to the client, i.e. the browser? send back the index.erb view file 
Spend a few minutes mapping out a domain model for a parking lot. How would you model the relationship between cars and spaces? How would you keep track of how long a car had been parked in a space? How would you keep track of how much money someone would need to pay for having parked a certain amount of time?Parking Garage app with 3 models: Car, Space and Parking. Parking is the joiner model, and is initialized with car_id, space_id, Parked?(default=true), rate_per_hour and the default timestamp  
      - Car has many parkings, and many spaces through parking

      - Space has many parkings, and many cars through parking.

     - When a Parking is created, it is initialized with a car_id, a space_id and a default Parked value of true. The timestamp created at would record when the parking starts. When the Parking is over, ie the car leaves the space, the Parked value would be switched to 'false' and timestamp updated at would record when the parking is over.

      - The money someone needs to pay for the time parked in a space would be calculated by: time parked (Updated at - Created at). round(2) * rate_per_hour