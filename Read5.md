# Procfile
Use a Procfile, a text file in the root directory of your application, to explicitly declare what command should be executed to start your app.

The Procfile in the example app you deployed looks like this:

web: node index.js
This declares a single process type, web, and the command needed to run it. The name web is important here. It declares that this process type will be attached to the HTTP routing stack of Heroku, and receive web traffic when deployed.

Procfiles can contain additional process types. For example, you might declare one for a background worker process that processes items off of a queue.

Right now, your app is running on a single web dyno. Think of a dyno as a lightweight container that runs the command specified in the Procfile.

You can check how many dynos are running using the ps command:

heroku ps
=== web (Free): `node index.js`
web.1: up 2014/04/25 16:26:38 (~ 1s ago)
### By default, your app is deployed on a free dyno.

To avoid dyno sleeping, you can upgrade to a hobby or professional dyno type as described in the Dyno Types article. For example, if you migrate your app to a professional dyno, you can easily scale it by running a command telling Heroku to execute a specific number of dynos, each running your web process type.


### Access the app again by hitting refresh on the web tab, or heroku open to open it in a web tab. You will get an error message because you no longer have any web dynos available to serve requests.


heroku local web to start it localy  `http://localhost:5000 `