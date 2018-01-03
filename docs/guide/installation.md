# Integrating Firebase

Using Firebase, developers can add a realtime backend to their Ember app without setting up a server. Firebase's Ember library EmberFire integrates directly with Ember Data, so all of the data for your app is automatically persisted.

Tom Dale, one of the creators of Ember, explains:

> With first-class support for Ember.js, Firebase developers can continue pushing the boundaries of what's possible in the browser by leaning on the strong architectural features of Ember that lead your app towards clean separation of concerns.
TOM DALE, CO-CREATOR OF EMBERJS

This guide assumes you are using EmberFire as an `ember-cli` addon. Not using ember-cli? Follow the instructions [here](without-ember-cli.md) to get started.

Firebase's realtime data synchronization is a great fit with Ember's frontend philosophy. Using EmberFire, we can interact with Ember Data as we normally would, and our app's data will automatically be persisted. Adding EmberFire to your `ember-cli` app is simple.


## 1. Install emberfire as an ember-cli addon

In order to use EmberFire in our project, we can run the following in our ember-cli app's directory:

```
$ ember install emberfire
```

This will add Firebase to your `bower.json` file and generate `app/adapters/application.js` for you with the following content:


```js
// app/adapters/application.js
import FirebaseAdapter from 'emberfire/adapters/firebase';
export default FirebaseAdapter.extend({
});
```


## 2. Configure your Firebase Database URL

We'll build a blogging app to demonstrate how to store and sync data with EmberFire. Full code for this app is available on GitHub.

```js
// config/environment.js
var ENV = {
  firebase: {
    apiKey: 'xyz',
    authDomain: 'YOUR-FIREBASE-APP.firebaseapp.com',
    databaseURL: 'https://YOUR-FIREBASE-APP.firebaseio.com',
    storageBucket: 'YOUR-FIREBASE-APP.appspot.com',
  }
```

You are now set up to use Ember Data as you normally would.

# Firebase Preview
If you have two firebase projects and would like to access both in a single application, you will need to use firebase preview. In your environment file you need to add firebasePreview which contains the configuration of your second firebase project:

```js
// config/environment.js
var ENV = {
  firebasePreview: {
    apiKey: 'xyz',
    authDomain: 'YOUR-FIREBASE-APP.firebaseapp.com',
    databaseURL: 'https://YOUR-FIREBASE-APP.firebaseio.com',
    storageBucket: 'YOUR-FIREBASE-APP.appspot.com',
  }
```

For emberfire to access this data, you need to pass the ```preview=true``` query into the URL.

### Continue reading

1. **Installation**
1. [User Authentication](authentication.md)
1. [Saving and Retrieving Data](saving-and-retrieving-data.md)
1. [Querying Data](querying-data.md)
1. [Relationships](relationships.md)
1. [Security Rules](security-rules.md)
1. [Using EmberFire without Ember CLI](without-ember-cli.md)
1. [Deploying to Firebase Hosting](deploying-to-firebase-hosting.md)
