[Back to main](readme.md)

-----

> 10/10

# npm install --save mongoose

# Connected to Mongoose

- Fill in the blanks: Rails is to ActiveRecord is to Postgres, as Node is to `_____` is to `_____`.
- What's the difference between `$ mongo` and `$ mongod`? What are they similar to in the Rails world?
- What's wrong with this sentence: "When you run `mongoose.Schema` it adds new columns to a table in your database."

![#](images/connected-to-mongo.png)

# Added seed data (to database)

![#](images/module-exports.png)

![#](images/seed-script.png)

-----
STOP
-----
> 10/20

# Shows DB candidates in candidates#index

- What's the purpose of the callback function in `Candidate.find().then(callback)`? Why is it necessary?

![#](images/db-candidates-in-index.png)

# Shows DB candidates in candidates#show

- What's the difference between `.find` and `.findOne`?

![#](images/db-candidates-in-show.png)

-----
STOP
-----
> 10/30

# npm install --save body-parser

- Why do we need `body-parser`?

![#](images/added-body-parser.png)

# Added nonfunctional post route

- How are `<form>` elements and `req.body` related?
- Why is it `req.body` and not `res.body`?

![#](images/form-in-index.png)

![#](images/add-post-route.png)

# Saves new candidate to database

- What's the difference between `res.send`, `res.render`, `res.json`, and `res.redirect`?
- Why would `res.json("hello")` throw an error?

![#](images/create-to-db.png)

-----
STOP
-----
> 10/40

# Updates a candidate in the database

- Why can't we use `app.put` or `app.patch` for an "update" route? How is the answer to this question related to HTML forms?
- How come `.findOneAndUpdate` has 3 arguments while `.create` has only 2?

![#](images/form-in-show.png)

![#](images/add-update-route.png)

# Deletes candidate from database

- Why can't we use `app.delete` for a DELETE route?
- Why shouldn't you use `app.get` for DELETE routes?

![#](images/delete-in-show.png)

![#](images/add-delete-route.png)

-----
STOP
-----
> 5/45

# Added procfile and Mongolab URL for deployment

- True or false: the environment variable for your Mongo database's location *must* be `MONGOLAB_URL`.
- What's the value of `process.env.NODE_ENV` on Heroku? On your computer?

![#](images/mongolab-url.png)

1. `$ git push heroku master`
- Go to www.mongolab.com and sign up / sign in
- Create a new "Single Node" database with the "Sandbox" tier
- Click on the database
- Click "Users"
- Create a new user. (This is *not* the user with which you logged in to Mongolab.) "User" in this context really means "an app that has access to your database". There's no need for security now; I used the username "test" with a password of "testerson".
- Copy the "To connect using a driver" URL from the top of the Users page.
- Set the URL as an environment variable called MONGOLAB_URL using `heroku config:set` as below, filling in the username and password you just created on the "Users" page. For example:
    ```
    $ heroku config:set MONGOLAB_URL=mongodb://test:testerson@ds015760.mlab.com:15760/yourappname
    ```
- `$ heroku run node db/seed.js`
- `$ heroku open`

-----
STOP
-----
> 15/60

# Added positions to candidate

- What's different about how we're storing Candidates and Positions here versus how we would do it in Rails with ActiveRecord?

![#](images/positions-schema.png)

![#](images/positions-seeds.png)

# Can add a position

- Why is `candidate.save` "inside" `Candidate.findOne`?

![#](images/positions-create-route.png)

![#](images/positions-create-form.png)

# Can delete a position

![#](images/positions-delete-route.png)

![#](images/positions-delete-form.png)

-----

[Back to main](readme.md)
