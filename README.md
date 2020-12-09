# Ember Tuto

## Install Ember
```
npm install ember-cli
```

## Start server
```
ember s
```

## Install Saas
```
npm install ember-cli-saas
```
In `ember-cli-build.js`, add this option in `app`:
```
sassOptions: {
  extension: "scss"
}
```

## Routing

#### Overview

URL: `http://localhost:4200/cart`

app/router.js
```
Router.map(function() {
  this.route('cart');
});
```

Component:
```
app/routes/cart.js
app/controllers/cart.js
app/templates/cart.hbs
```

#### Types of routes
```
                                             Nested route (/clothes/t-shirt)
                                           /
                    Basic route (/clothes) 
                  /                        \
Application route                            Index route (/clothes) : default page
                  \
                    Dynamic route
                  \
                    Not found route
```


#### Generate basic route
```
ember g route <name>
```

#### Generate nested route
```
ember g route <route>/<nested-route>
```

#### Generate index route
```
ember g route <route>/index
```

#### Generate dynamic route
```
ember g route <name>
```
Change path in `app/router.js`:
```
this.route('name', { path: '/name/:id' });
```
In `route/<name>.js`, add:
```
model(params){
  const {
    item_id
  } = params;
  return item_id;
}
``` 
In the template, you can access the value with `{{this.model}}`. What happen with several parameters ?

#### Generate Not found route
```
ember g route not-found
```
In `router.js`:
```
this.route('not-found', { path: '/*path'})
```

#### Routes and controllers
```
Route ------- model -------> Controller
 |  \                            /
 | model                properties & actions
 |     \                        /
 |      \---> Template <-------/
 |
\|/
predefined methods: beforeModel, afterModel, redirect, setupController
```

### Component

```
ember g component <name>
ember g component <name>/<subname>
```

In template, use `<Name/>` and `<Name::Subname/>`.


