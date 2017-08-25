# g-contacts
Node.js wrapper for the Google Contacts API.

# Install
  
  npm install g-contacts --save
  
# Usages

```javscript
var googleContacts = new GoogleContacts(CLIENT_ID, CLIENT_SECRET);
var credentials    = {
  access_token : "ya29.GlyZBE5XzlI43OMOWbZueT",
    expiry_date  : 1501494739000, //true
    refresh_token: "1/wmz9DHCBg0CNtmKZVH_Wg",
    token_type   : "Bearer"
};

googleContacts.setUserCredentials(credentials);

googleContacts.getContacts(function (error, data) {
    console.log("Error " + error);
    console.log("Data " + JSON.stringify(data));
});
```
 
