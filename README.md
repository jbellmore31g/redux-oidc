# redux-oidc 
[![Build Status](https://travis-ci.org/maxmantz/redux-oidc.svg?branch=master)](https://travis-ci.org/maxmantz/redux-oidc)

A package for managing OpenID-Connect authentication in ReactJS / Redux apps.

### Installation
`npm install --save redux-oidc`

#### Peer dependency
This package has [oidc-client-js](https://github.com/IdentityModel/oidc-client-js/tree/master) as its peer dependency.
In order to install this run:

`npm install --save oidc-client`

In addition there is a peer dependency for [immutable.js](https://facebook.github.io/immutable-js/), if you want to use it.

### Description

This package handles [OpenID-Connect](http://openid.net/connect/) authentication in [redux](http://redux.js.org/) apps. It enables redux apps to authenticate with an external OIDC authentication provider and handles the actions of the OpenID [implicit flow](http://openid.net/specs/openid-connect-implicit-1_0.html).

It uses the oidc-client-js library to manage OpenID Connect functionality.

It contains the following parts:
- *oidcMiddleware*: [redux middleware](http://redux.js.org/docs/advanced/Middleware.html) to automatically check whether or not the current user is signed in & trigger the authentication flow,
- *CallbackComponent*: A react component processing the callback from the OpenID-Connect provider,
- *reducers & actions*: reducers and actions to handle OIDC events,
- *helpers*: create helpers to manage the oidc-client-js library

### Reasons developing version 2
- the old version was relying on the `oidc-token-manager` which was not npm compliant and had to be manually maintained, this version now uses the [oidc-client-js](https://github.com/IdentityModel/oidc-client-js/tree/dev) library which is written in ES6, fully tested and npm compatible,
- the old version also relied heavily on creating new instances of the token manager, which could cause unexpected behavior when more than one instance was active at the same time - this version only needs a single instance of `UserManager` to work,
- the old version had little which pronounced the *redux* in `oidc-redux`. This version offers a reducer including dispatchable actions to handle OIDC interactions.

### Version 1
This is the page for version 2 of this package. For version 1 check out the [v1 branch](https://github.com/maxmantz/redux-oidc/tree/v1).

### Documentation

Check out the [wiki](https://github.com/maxmantz/redux-oidc/wiki) for further information.

### Sample app
There is a sample application demonstrating the use of this package [here](https://github.com/maxmantz/redux-oidc-example).

### Tests
`npm run test`
