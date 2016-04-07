# WhenPresident Walkthrough

# npm install --save mongoose

# Connected to Mongoose

- Fill in the blanks: Rails is to ActiveRecord is to Postgres, as Node is to `_____` is to `_____`.
- What's the difference between `$ mongo` and `$ mongod`? What are they similar to in the Rails world?
- What's wrong with this sentence: "When you run `mongoose.Schema` it adds new columns to a table in your database."

![#](images/connected-to-mongo.png)

# Added seed data (to database)

![#](images/module-exports.png)

![#](images/seed-script.png)

# Shows DB candidates in candidates#index

- What's the purpose of the callback function in `Candidate.find().then(callback)`? Why is it necessary?

![#](images/db-candidates-in-index.png)

# Shows DB candidates in candidates#show

- What's the difference between `.find` and `.findOne`?

![#](images/db-candidates-in-show.png)

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

# Added procfile and Mongolab URL for deployment

- True or false: the environment variable for your Mongo database's location *must* be `MONGOLAB_URL`.
- What's the value of `process.env.NODE_ENV` on Heroku? On your computer?

![#](images/mongolab-url.png)

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
