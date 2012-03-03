# base12
      
[12factor.net](http://12factor.net) app boilerplate for [node.js](http://node.js), built on [express 3](http://expressjs.com)

```shell
$ git clone git://github.com/hunterloftis/base12.git projectname
$ cd projectname
$ npm install
$ node run
```

**12 Factor**
- Painlessly follow Ryan Dahl's 'gospel' for production-ready node.js apps (12factor.net)

**Cloud Deployments**
- Deploy to the cloud easily and immediately (joyent, heroku, amazon, linode, rackspace, nodejitsu)

**Structure**
- Always know where things go. A proven MVC architecture on top of express.

**Express 3**
- Leverage the newest version of the most popular app framework for node.js.

**Not Rails**
- We believe that, if Rails is best for your project, you should use it.
Instead, base12 embraces the node.js way: light processes, shallow inheritance, simple interfaces, and the chain-of-responsibility pattern.

## Where stuff goes

```
app
  /controllers      -- controllers are automatically loaded (user.js -> app.controllers.user)
  /lib              -- app-specific modules (default: routes.js, middleware.js, locals.js)
  /middleware       -- middleware is automatically loaded (auth.js -> app.middleware.auth)
  /models           -- models are automatically loaded (project.js -> app.models.project)
  /public           -- static files are hosted here
  /shared           -- isomorphic (client/server) files are hosted here
  /views            -- view templates are automatically loaded via express
  index.js          -- starts your application with `base12.app()`

doc                 -- documentation
env                 -- named environment configurations (eg `staging`, `deployment`)
lib                 -- non-npm-published generic modules
scripts             -- scripts (eg admin, deployment, migrations)
test                -- tests (vows by default)
tmp                 -- your app can store temporary files here

package.json        -- npm package.json plus application constants
.env.js             -- created by `npm install`, local environment config

build.js            -- builds assets
run.js              -- runs your app
cycle.js            -- watches local files and builds/runs on changes (for development)
```

When base12 starts, it runs `/index.js`. By default, `/index.js` uses `base12.balance()`
to balance multiple app processes via `cluster` (1 process per cpu).

Each process runs `/app/index.js`, which creates a new app with `base12.app()`. The `app` instance is passed into all modules. 

Once all modules have run, the app starts listening for requests.

## Writing controllers, models, middleware, and libs

## Building on Express 3

## Common commands

## The 12 Factors


