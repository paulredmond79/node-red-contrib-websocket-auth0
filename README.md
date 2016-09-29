# node-red-contrib-websocket-auth0
A web-socket with Auth0 authentication support.

[![npm version](https://badge.fury.io/js/node-red-contrib-websocket-auth0.svg)](https://badge.fury.io/js/node-red-contrib-websocket-auth0) ![codeship](https://codeship.com/projects/dfcc3910-2420-0134-486b-76d3d72b136a/status?branch=master)

Install
-------

Run the following command in the root directory of your Node-RED install

    npm install node-red-contrib-websocket-auth0


Usage
-----

**Edit the websocket-listener-auth0 node with your *Domain* value above in the Account setting panel.**

- By default, it checks for the valid auth0's token and pass the request to the downstream node.
- Request is authorized if the **role** value is set to the auth0 user's role value. Usually setup by https://manage.auth0.com/#/rules
- Request is authorized if the **group** value is set to the auth0 user's group value. Usually setup by installing the **Auth0 Authorization 1.4 extension**

**Try to get your auth0's id_token from your auth0 application and pass it into the Authorization Header**

Currently it supports only **Bearer** token which is taken from **id_token** parameter.

```javascript
curl -i http://127.0.0.1:1880/test -H "Authorization: Bearer {{auth0-id-token}}"
```
