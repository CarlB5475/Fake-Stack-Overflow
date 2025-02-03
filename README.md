# Fake Stack Overflow
James Carl Nanas

CSE316 - Software Development - Fall 2023

Contributors:
- James Carl Nanas
- Saatvik Sandal

## Summary
A Stack Overflow clone web project for my Software Development class that helped me learn the tech stack for web development. I collaborated with a fellow classmate on this project.

## What I Learned
- Frontend development tech stack:
    - HTML
    - CSS
    - JavaScript
    - React
- Backend development tech stack:
    - Node.js
    - Express
    - MongoDB

- Use the axios library to make HTTP requests from the client to server to fetch and perform CRUD operations on the following data:
    - User accounts
    - Tags
    - Question posts
    - Answers
    - Comments
- Use bcrypt to encrypt passwords into the MongoDB database for security.
- Use express-session to handle user accounts logging in to the website.

### Modifications
I have now utilized Docker to containerize this project's frontend, backend, and database. They can all run and communicate with each other seamlessly independent of the user's dev environment for ease of use running it. This experience has taught me how to use Docker in my software development.

# Instructions to setup and run project
## Prerequisites
The only thing you need to have installed is [Docker](https://www.docker.com) in order to run this application locally. You don't need to install packages for the client or server, and don't need to run a MongoDB database locally.
## Setup
Navigate to the project directory, and to initialize and run the application for the first time, run the following command.
```
$ INIT_DB=true ADMIN_USERNAME=<username> ADMIN_PASSWORD=<password> docker-compose up --build -d
```

**Note:** If you use CMD or Powershell on Windows, use the following commands respectively instead.

CMD:
```
$ set INIT_DB=true
$ set ADMIN_USERNAME=<username>
$ set ADMIN_PASSWORD=<password>
docker compose up --build -d
```

Powershell:
```
$ $env:INIT_DB="true"
$ $env:ADMIN_USERNAME="<username>"
$ $env:ADMIN_PASSWORD="<password>"
$ docker compose up --build -d
```
You will have to set `INIT_DB=false` for the CMD and Powershell methods afterwards again if you don't wait to reset the database again. You'll also need to modify the `ADMIN_USERNAME` and `ADMIN_PASSWORD` environment variables if you want to have a different admin username and password for initialization.

This command will run the `init.js` script to reset the database and populate it with sample data before running the application. Here's the sample user accounts you can use:
- Admin: `username: admin (default) | password: password (default) | email: yomama@gmail.com`
- Regular user: `username: joeshmo | password: supersecret | email: mybrainhurts@gmail.com`
- Regular user: `username: john doe | password: supersecret2 | email: johndoe@gmail.com`

If you want to run the application without initialization, then run the following command.
```
$ docker compose up -d
```

To access the webite, go to http://localhost:3000.

To access the database, go to http://localhost:8081.

To stop running the application, run the following command.
```
$ docker compose down
```

# Project Contributions
## Team Member 1 Contribution
James Nanas
- In charge of planning the front-end design of the Fake Stack Overflow website.
- Front-end stuff:
    - Implemented the front-end design for the "Welcome Page"
    - Implemented the user registration portion of the "Welcome Page".
    - Implemented the "Login Page" and the login feature.
    - Implemented the refreshing of the home page when the user is logged in.
    - Added the "Continue as Guest" button functionality.
    - Added the "Log Out" button.
    - Adding the "Prev" and "Next" buttons in home page for displaying questions.
    - In charge of designing the "User Profile Page" and its functionalities.
    - Revamped the "Ask Question Page" to meet the new requirements.
    - Implementing the editing function for the "Ask Question Page"
    - Fixed constant looping of componentDidUpdate() in "Fake Stack Overflow" component.
    - Finished implementing the editMode version of "Ask Question Page".
    - Implemented the deletion of users from the admin.
- Back-end stuff:
    - Added the Users and Comments schemas to the http requests in server.js
    - Added a user-specific http request that checks the password of a login is correct using bcrypt.
    - Added many user-specific, question-specific, and tag-specific http requests.
    - Fixed up init to hash passwords as well.

## Team Member 2 Contribution
Saatvik Sandal
- Created the UML Diagram
- Added User schema and Comment schema to DB.
- Created init.js functionality and test data.
- Added hashing functionality to server.js when registering a new user.
- (Half) added cookie ability
- Updated init to hash passwords before creating it.
- Added express-session functionality, and user information storage in cookie.
- Added prev/next button functionality to all pages
- Finished adding it to schema, finished functionality where it gets added during add question/answer form 
- Added component to question items
- Created comment component and added comment functionality to answers and questions, and upvote functionality.
- Added voting and reputation functionality entirely
- Separated functionalities for guest and logged-in users across all options

# Old Notes
## To-do List
### James Nanas
- Create the following pages:
    - "User Profile Page" (for regular user)
        - Add the following user displays:
            - User Answers
    - "User Profile Page" (for admin)
        - Display all users in the system.
- Existing pages to work on:
    - "Home Page"
        - Add the number of votes on each question displayed in home page.
        - (OPTIONAL) Fix graphical glitch on search as well.
    - "Tags Page"
        - (OPTIONAL) Fix graphical glitch on displaying questions associated with a tag.
    - "Answers Page"
        - Fix graphical glitches
        - Display the set of tags in the answer page as well.

## Additional Notes
Added use cases : 1, 2, 3, 4, 5, 6, 7, 8, 13

### Things to do for 316: 
- Fix next button to complete roundtrip
- Add changes to (tags and answers in users) init.js and the diagram
- Add votes to question (and any other missing details here ------>   For each question in the list it displays, the question title, question summary, the list of associated tags, the no. of times it has been viewed and voted, the no. of answers it has, the username of the questioner and the date it was posted.)
- Need to add the number of votes to answer (use case 9) (use case 10)
- Both registered/guest: Need to add comments to question in the answer page (link of question clicked) (use case 9) (use case 11 and 12 (depends on if logged in))
- Both registered/guest: Need to add next/prev buttons for answers in answer page (5 answers at a time, next button does roundtrip) (use case 9)

- For guest: remove option to add new answer in answer page and make sure they dont have option of upvote or downvote. (use case 9)
- For registered: New answer button (done) and add following:  (use case 10)
    - The question and each answer has options to upvote and downvote the question or answer. Upvoting increases the vote by 1 and downvoting decreases the vote by 1. Upvoting a question/answer increases the reputation of the corresponding user by 5. Downvoting a question/answer decreases the reputation of the corresponding user by 10. A user can vote if their reputation is 50 or higher 
- For guest: Add comments to answers and questions (use case 11) 
- For registered: Add comments to answers and questions but with options when logged in. (use case 12)
- User profile: Use case 14 and 15 depending on admin or not.






Live edits for Saatvik: DONE MINUS guest functionality
UNFINISHED --

Still need to make it so that if the user is a guest one they cant use the buttons. 
start on the upvote for answers and questions - reputation system
