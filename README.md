Description
===========

[Node.js](http://nodejs.org/) wrapper for the [Google Contacts API](https://developers.google.com/google-apps/contacts/v3/).

Requirements
============

* [Node.js](http://nodejs.org/) -- v0.10.32 or newer

Installation
============
  
    npm install g-contacts
  
Examples
========

* Set user's credentials. If you provide a refresh_token and expiry_date (milliseconds since the Unix Epoch) and the access_token has expired, the access_token will be automatically refreshed and the request is replayed.

```javascript
var GoogleContacts = require("g-contacts");

var googleContacts = new GoogleContacts(CLIENT_ID, CLIENT_SECRET);
var credentials    = {
  access_token : "ya29.GlyZBE5XzlI43OMOWbZueT",
  expiry_date  : 1501494739000,               // Set it true to force a refresh always.
  refresh_token: "1/wmz9DHCBg0CNtmKZVH_Wg",
  token_type   : "Bearer"
};

googleContacts.setUserCredentials(credentials);
```

* Fetch all the contact's info such as 'name', 'email id', 'contact id' and 'contact type'.

```javascript
googleContacts.getContacts(function (error, data) {
    console.log("Error " + error);
    console.log("Data " + JSON.stringify(data));
});
```

* Fetch the contact's info such as 'name', 'email id', 'contact id' and 'contact type' for a given contact id.

```javascript
var options = {
  contact_id: '123er45456'
};
googleContacts.getContacts(options, function (error, data) {
    console.log("Error " + error);
    console.log("Data " + JSON.stringify(data));
});
```

* Fecth the contact's info using query parameters.

```javascript
var options = {
  query_params: {
    q: "ram@gmail.com"
  }
};
googleContacts.getContacts(options, function (error, data) {
    console.log("Error " + error);
    console.log("Data " + JSON.stringify(data));
});
```

TODO
====

* Add a new contact.
* Updation of a contact.
* Deletion of a contact.

