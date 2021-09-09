## Installing dependencies

```
npm i express mongoose ejs

npm i --save-dev nodemon

```

- to use nodemon> package.json > scripts > "{"devStart": "nodemon server.js"}

## Set up server & main page

```
touch server.js
```

```
mkdir views >> touch index.ejs
```

## Set up Routes

```
mkdir routes >> touch article.js
```

1. route for creating new article

- router.get('/new')

```
cd views > mkdir articles > touch new.ejs
&&
touch _form_fields.ejs
```

- \_form_fields will be partial, reusuable component

2. route for posting(saving) new article

- router.post('/')
- require mongoose in server.js
- connect to NoSQL DB (mongoDB)

```
mongoose.connect('mongodb://localhost/blog')
```

- create model(schema) for storing article

```
mkdir models > touch article.js
```

- require in the created model into routes>> article.js
- in server.js >>

```
app.use(express.urlencoded({extended: false}))
```

- in router > article.js, create a new route for showing article by id. app.get('.)

2. Delete Route

```
npm i method-override
```

- server.js > require

```
app.use(methodOverride('_method'))
```

- to use > form

```
action="/articles/<%=article.id%>?_method=DELETE" method="POST"

```

3. Edit Route

## Heroku deployment

- heroku login
- add to script: "start": "node server.js"
- add "engines" : {
  "node": ">=10.0.0"
  }
