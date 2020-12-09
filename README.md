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

### Routing

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
