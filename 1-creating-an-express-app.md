# When President Express Setup

# npm init && npm install --save express

> [cfa8443](https://www.github.com/ga-wdi-exercises/whenpresident/commit/cfa8443)

When creating a new Express app, the first steps you'll always do are:
1. Create and `cd` into a new folder
- `$ npm init`, then hold down "Return" to answer "yes" to all the questions
- `$ npm install --save express`
- `$ echo "node_modules" > .gitignore`

When downloading someone else's Express app, you will simply:
1. `$ npm install`

Questions:
- What is NPM?
- What does `package.json` do?
- What does the `--save` in `npm install --save express` do?
- Why is putting `node_modules` in `.gitignore` important?

### [npm init && npm install --save express: `.gitignore`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/cfa8443/.gitignore)
![npm init && npm install --save express, .gitignore](_DIFFSHOTS/npm-init-npm-install-save-express.-gitignore.png)
### [npm init && npm install --save express: `package.json`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/cfa8443/package.json)
![npm init && npm install --save express, package.json](_DIFFSHOTS/npm-init-npm-install-save-express.package-json.png)
 
# Added index.js

> [c39c5a7](https://www.github.com/ga-wdi-exercises/whenpresident/commit/c39c5a7)

- What does `nodemon` do?
- What does `require` do?
- What's the difference between `require("hello")`, `require("./hello")`, and `require("./hello.js")`?
- Note the `()` at the end of `express()`. This means `require("express")` must be returning what kind of object?
- What does the `.get` in `app.get` indicate?
- What do `req` and `res` stand for?
- What happens if you don't include `res.send`?
- What is `3001`, and how does it affect what you do in your browser?

### [Added index.js: `index.js`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/c39c5a7/index.js)
![Added index.js, index.js](_DIFFSHOTS/added-indexjs.index-js.png)

-----
# STOP
-----
 
# Download HBS

```bash
$ npm install --save hbs
```

```js
var hbs = require('hbs');
```

- Whenever you `npm install --save` something, you'll also probably need to do what?
- Whenever you `require` something, you'll probably need to do what first?

 
# Added views

- `<%= yield %>` in Rails is like what in Handlebars?
- What's the difference between a `.hbs` file and a `.html` file?

### [Added views: `views/app-welcome.hbs`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/e13f24f/views/app-welcome.hbs)
![Added views, views/app-welcome.hbs](_DIFFSHOTS/added-views.views-app-welcome-hbs.png)
### [Added views: `views/layout-main.hbs`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/e13f24f/views/layout-main.hbs)
![Added views, views/layout-main.hbs](_DIFFSHOTS/added-views.views-layout-main-hbs.png)
 
# Configured handlebars

- What's the difference between `res.send` and `res.render`?

```js
app.set('view engine', 'hbs');
app.set('views', './views');
```

Change send to render and render the app-welcome view.

```js
app.get('/', (req, res) => {
  res.render('app-welcome');
});
```
 
-----
# STOP
-----

# Added express.static and CSS

- What do the two arguments in `app.use` in this snippet do?
- Why is `app.use` called "middleware"?
- If I write `app.use("/wombat", express.static("chicken"))`...
  - In which folder should I put all my CSS files?
  - When I `<link>` to my CSS, with what will the `href` path begin?
  
Set up express to point to the public static files.

```js
app.use(express.static(__dirname + '/public');
```

Create a public folder and css folder within it for a `main.css` file.
  
```bash
$ mkdir public
$ mkdir public/css
$ touch public/css/main.css
```

Include the link to the file in the head of the `layout.hbs` file.

```html
<head>
    <meta charset="utf-8">
    <title>When President</title>
    <link rel="stylesheet" href="/css/main.css">
</head>
```
 
# Added front-end Javascript

```bash
$ mkdir public/js
$ touch public/js/script.js
```

Include this also in the head of the `layout.hbs` file.

```html
<head>
    <meta charset="utf-8">
    <title>When President</title>
    <link rel="stylesheet" href="/css/main.css">    
    <script src="/js/script.js" charset="utf-8"></script>
</head>
```

We can write a `console.log('I am working')` in our js file and test it in the browser console to see if it works.

-----
# STOP
-----

# Add a candidates#index route

> [3da2c67](https://www.github.com/ga-wdi-exercises/whenpresident/commit/3da2c67)

- What does the second argument in `res.render` do? What kind of data type should it be?

```bash
$ touch views/candidates-index.hbs
```

### [Added candidates#index route: `views/candidates-index.hbs`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/3da2c67/views/candidates-index.hbs)
![Added candidates#index route, views/candidates-index.hbs](_DIFFSHOTS/added-candidatesindex-route.views-candidates-index-hbs.png)

### [Added candidates#index route: `index.js`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/3da2c67/index.js)
![Added candidates#index route, index.js](_DIFFSHOTS/added-candidatesindex-route.index-js.png)
 
# Add fake data

> [0e2c37d](https://www.github.com/ga-wdi-exercises/whenpresident/commit/0e2c37d)

- What is `module.exports` and how is it related to `require`?

```bash
$ mkdir db
$ touch db/connection.js
$ touch db/seeds.json
```

### [Added fake data: `db/connection.js`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/0e2c37d/db/connection.js)
![Added fake data, db/connection.js](_DIFFSHOTS/added-fake-data.db-connection-js.png)

You may copy and past the seed data into the seed.json file.

```json
[
 {
  "name": "Steve",
  "year": 2024
 },
 {
  "name": "Obama",
  "year": 2008
 },
 {
  "name": "Dubbya",
  "year": 2000
 }
]
```

### [Added fake data: `index.js`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/0e2c37d/index.js)
![Added fake data, index.js](_DIFFSHOTS/added-fake-data.index-js.png)
### [Added fake data: `views/candidates-index.hbs`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/0e2c37d/views/candidates-index.hbs)
![Added fake data, views/candidates-index.hbs](_DIFFSHOTS/added-fake-data.views-candidates-index-hbs.png)
 
# Add #each in index

> [6f3ebaf](https://www.github.com/ga-wdi-exercises/whenpresident/commit/6f3ebaf)

- What's the difference between how you begin an end an `each` loop in Handlebars?
- How is Handlebars' `#each` similar to Ruby's `.each`?

```html
<h2>{{candidates.length}} Candidates</h2>

{{#each candidates as |candidate index|}}
<h3>
  <a href="/candidates/{{index}}">{{candidate.name}}</a> for president in {{candidate.year}}
</h3>
{{/each}}
```
 
-----
# STOP
-----

# Add a candidates#show route

> [7bbe33d](https://www.github.com/ga-wdi-exercises/whenpresident/commit/7bbe33d)

```bash
$ touch views/candiates-show.hbs
```

### [Added candidates#show route: `views/candidates-show.hbs`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/7bbe33d/views/candidates-show.hbs)
![Added candidates#show route, views/candidates-show.hbs](_DIFFSHOTS/added-candidatesshow-route.views-candidates-show-hbs.png)
 
Next add the route to the `index.js` file:

```js
app.get('/candidates/:id', (req, res) => {
  res.render('candidates-show', {
    candidate: db.candidates[req.params.id]
  });
});
```
 
-----
# STOP
-----

# Deploying to Heroku

> [17a28af](https://www.github.com/ga-wdi-exercises/whenpresident/commit/17a28af)

- What does a Procfile do?
- What's the point of environment variables?
- How do you access environment variables?

```bash
$ touch Procfile
```

### [Deploying to Heroku: `Procfile`](https://www.github.com/ga-wdi-exercises/whenpresident/blob/17a28af/Procfile)
![Deploying to Heroku, Procfile](_DIFFSHOTS/deploying-to-heroku.Procfile.png)

We next need to add `process.end.PORT` as an optional port when deploying to Heroku.

```js
app.listen(process.env.PORT || 3001, () => {
  console.log('//********************//');
  console.log('//*LISTENING ON 3001**//');
  console.log('//********************//');
});
```

Then we need to set up `package.json` to use a specific node version for its server engine right below the dependencies.

```json
"dependencies": {
    "express": "^4.14.0",
    "hbs": "^4.0.1"
  },
  "engines": {
    "node": "6.3.1"
  }
```
 
