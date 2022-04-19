# SpaceBook

### Overview and Brief

In a group (3 people) we were asked to create a full-stack app in 9 days. The front-end was to be built using React, and the back-end using Node.js, Express and MongoDB.

Our team decided to build a booking website and community for space travel called Spacebook. We would highlight the 8 planets in our solar system as travel destinations, and allow customers to book trips. 

### Deployment Link

https://space-book-sei61.herokuapp.com/  


### Technologies Used

#### Back-end

Express, MongoDB/Mongoose, Bcrypt, JWT (jsonwebtoken), Axios

#### Front-end
JSX (HTML5 in React), SCSS, JavaScript (ES6), Node.js, Bootstrap, Axios

#### Dev Tools

VScode, Yarn, Insomnia, GitHub, Heroku (deployment), Figma (planning)


### Planning and preparation

This was for all of us our first time building a full-stack app so we decided that we would code the back-end together through a mix of VScode live-share and zoom screen-sharing. 

During front-end development we would then separate tasks to handle individually. 
We used Trello to create a checklist for our planned build. 


![alt text](/client/assets/project3-1.png)


#### Wireframing

We used Figma to make a wireframe for the front-end of our site, with the various pages we planned to build. We wanted a main page with the 8 different planets on a carousel that could be scrolled through. Each one could then be clicked to open the planet page and from there bookings could be made. We also planned to have login and profile pages for users, and also a special offers page.



![alt text](/client/assets/project3-2.png)

### The Back-End

The back-end consisted of a locally-seeded database, secure routes, controllers, routes and models.
We started by creating the index.js file and writing our ‘startServer’ function. This function connects to our chosen MongoDB server, converts the body of the request to JSON then uses our routes which we defined in our routes file.
Next we targeted the models, for the planet model we defined two schemas. The ‘planetSchema’ had a number of keys with nested data, we focused on seeding ‘offers’ and ‘imageGallery’, both were nested arrays. We also gave each planet an average review rating. To do this we attached a virtual field to the planet schema that used the reduce method to calculate the mean.



![alt text](/client/assets/project3-3.png)


The ‘reviewSchema’ referenced the logged-in User to populate its owner field.


![alt text](/client/assets/project3-4.png)


For the User model we wrote the Schema then gave the Schema three additional virtual fields to handle the users ‘reviewed planets’, ‘wish list’ and ‘booked trips’. 


![alt text](/client/assets/project3-5.png)


We also used a virtual field to set the password confirmation then we used bcrypt to hash/validate the password. 


![alt text](/client/assets/project3-6.png)

![alt text](/client/assets/project3-7.png)


We then focused on the routes and controllers. We added Create, Read, Update, Delete routes and their related controller functions. To return our full dataset we populated our GET requests with ‘owner’ and ‘reviews’ to return each planet's related data.


![alt text](/client/assets/project3-8.png)


Finally we seeded our database with a few planets and wrote our seedDatabase function to test out our routes on Insomnia.

### The front-end

We split the front-end build into individual tasks. I built the register, login and planet details page, where each planet showcased what it had to offer. The login and register page were fairly standard pages, which I also styled with our space theme. I was pleased with the following work I did to produce the planet details page.


![alt text](/client/assets/project3-9.png)


![alt text](/client/assets/project3-10.png)


This page took up most of my time with the front-end. The details of each planet were pulled from our back-end database, using an Axios get request and React useState.


![alt text](/client/assets/project3-11.png)


I then produced a planet details card to outline the key features of each planet from our database.


![alt text](/client/assets/project3-12.png)


Our planet pictures were imported from the NASA website. I pulled the images from our database and then built a feature that allowed the user to click on the photo to enlarge. When the photo was clicked a second time, the page returned to its original form.


![alt text](/client/assets/project3-13.png)


This feature was built using React useState and by changing the class of the image when the picture was clicked, using Onclick.


![alt text](/client/assets/project3-14.png)


In CSS I styled the photo to be enlarged and take up most of the page. The main page is still somewhat visible in the background to allow the user to see that they have not left the planet details page. 
Below is the CSS for my spotlight container, which was the class used to style the large enlarged image. 



![alt text](/client/assets/project3-15.png)


### Challenges

Wishlist: We had difficulty utilising local storage to add the user’s wishlist on the front-end.

Planet Carousel: We were ambitious to try to use a moving circular carousel of planets on our homepage. This took up a large amount of time from one of our team members, and we all struggled with finding a solution to this.

Git: This was our first time using Git as version control, and to collaborate. We spent a considerable amount of time fixing merge conflicts and going over the steps to push and pull our various branches. It was the first time I had really seen the value of Git, and also the challenges of working on individual pages in a group project can be. 

Communication: Everybody had their own ideas on how the project should look and function. Bringing these ideas together proved challenging at times, particularly with the styling/ CSS work. It emphasised to me just how important communication is in software development. 


### Bugs

The Planet Carousel Is still not performing exactly how we planned. The planets are not 3D as they revolve, instead appearing paper-thin as they revolve from front to back. 


### Wins and Key Learnings

Git - Understanding and improving my use of Git. This project really helped with this. 

Planning - We spent the whole first day of the project wireframing on Figma. This was the first large full-stack project I have been involved with. It really highlighted the benefits of proper planning, communication and teamwork.

Building a functioning full-stack app for the first time, and being able to successfully join a back-end with a front-end. We were only 8 weeks into our programming course, and I think this was a big achievement. 

Resizing the planet images using CSS and UseState. I was really pleased with how this functioned and looked. 

### Future Improvements

Finish the User profile page and populate it with their reviews and booked trips.

Set-up the booking functionality, saving users booked trips to local storage.

Add a button to toggle fictional planets on the homepage.