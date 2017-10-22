# Continous Integration - Heroku, Travis-ci, Github, and Mlab
Purpose: Use for teaching thinkful students

## Demo Links
* [Mlab node-restaurants-app ](https://mlab.com/databases/node-restaurants-app/collections/restaurants) - Database in Mlab
* [Heroku restaurants app](https://limitless-fjord-80961.herokuapp.com/restaurants) - App run in Heroku
* [Github Restaurant app](https://github.com/jpmariano/node-restaurants-app-mongoose) - Code Repo in Gihub
* [travis-c node-restaurants-app-mongoose](https://travis-ci.org/jpmariano/node-restaurants-app-mongoose) - Automated Testing

## Installing Locally
* Clone Locally [Github Restaurant app](https://github.com/jpmariano/node-restaurants-app-mongoose)
* Run NPM Install ```npm install```
* Open Terminal Run Mongo DB ```mongod```
* In your current App Folder, Run another terminal ```mongoimport --db restaurants-app --collection restaurants --drop --file primer-dataset.json```
* Run Node Locally: ```npm start```
* Open post man and do a Get Request: localhost:8080/restaurants

## Creating Database in Mlab
* Creat a Database - node-restaurants-app
* Add Database User - Note: Remember Username and Password for later use 
* Click on Tools and see the code use for Import: ```mongoimport -h ds229465.mlab.com:29465 -d node-restaurants-app -c <collection> -u <user> -p <password> --file <input file>```
* Import primer-dataset.json file into Mlab.In your current app folder, open a terminal and run: ```mongoimport -h ds229465.mlab.com:29465 -d node-restaurants-app -c restaurants -u <user> -p <password> --file primer-dataset.json```

# Pushing the Code to a Node Server - Heroku 
* In your current app folder Run ```heroku create``` 
* Push your local code to Heroku ```git push heroku master```
* Start a Dyno(lightweight Linux containers) on your server ```heroku ps:scale web=1```
* Connect Heruko and Mlab: Go to Heroku in your browser, and click your app. then click Settings => Reveal Config Vars. There, add an entry for DATABASE_URL, pasting in the database URL from step 1 after subbing in your username and password: ```mongodb://<dbuser>:<dbpassword>@ds99999.mlab.com:9999/node-restaurants-app```. This Variable should match with config.js process.env.DATABASE_URL .




