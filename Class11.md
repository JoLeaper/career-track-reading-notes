# Class 11 Reading: Authentication

## User Modeling
- User Models should NEVER be sent to client applications.
- If users need to view personal information, it is best practice to create a separate profile model to hold onto the data that needs to be seen and limit access to the Profile model. Prevents users from accidentally or maliciously gaining access.

## Cryptography
- Science of encoding messages so that the only one that can read them is a person with a decoder (the information that can be used for decoding ).
- Cryptanalysis is the science of decoding messages without the proper key.

## Hash Algorithms
- Short for Cryptographic Hash Algorithm.
- Takes data and produces a hash that is hard to reverse.
- The same data will produce the same hash (I.E. username and passwords)
- Checks integrity of data.

## Cypher Algorithms
- Short for Cryptographic Hash Algorithm.
- Takes data AND a key to produce encrypted data. Can be reversed using the same key.

## Basic Authorization
```js
let encoded = window.btoa('someusername:P@55w0rD!')
// c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==

let decoded = window.atob('c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==');
// someusername:P@55w0rD!

request({
  method: 'GET',
  url: 'https://api.example.com/login',
  headers: {
    Authorization: `Basic ${encoded}`,
  },
})
.then(handleLogin)
.catch(handleLoginError)
```

```js
let base64 = require('base-64');

let string = 'someusername:P@55w0rD!';
let encoded = base64.encode(string); // c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==
let decoded = base64.decode(encoded); // someusername:P@55w0rD!
```