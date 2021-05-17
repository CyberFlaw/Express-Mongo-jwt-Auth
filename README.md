# @cyberflaw/express-mongodb-jwt @2.1.1

![image info](https://img.shields.io/github/issues/CyberFlaw/Express-MongoDB-JWT-Auth)
![image info](https://img.shields.io/github/forks/CyberFlaw/Express-MongoDB-JWT-Auth)
![image info](https://img.shields.io/github/stars/CyberFlaw/Express-MongoDB-JWT-Auth)

<h4>A small package which makes authentification using express-mongodb and jwt much simpler. The only effort is to build your own mongoose.Schema and set values for a few json keys. More features will be added soon...

<br/>
<br/>
<h2> What's New?
<h4>
<ul>
<li> Added .gitignore support for environment variables
<li> Added a default mongoose.Schema
<li> Updated the documentation
</ul>

<br>

<h2> How to Configure:
<h4>
<ol>
<li>

Run `npm i express mongoose jsonwebtoken`

<li>

Run `npm i @cyberflaw/express-mongodb-jwt`

<li>

Make a file with name **config.json**
in the root directory

<li>Populate the JSON with the appropriate schema 
<br>

    {
        schemaPath: "path of your mongoose.Schema for your user",
        jwt:{
            expiresIn: "refer jwt documentation"
        }
    }

schemaPath can be left out to use the default schema which is:

```
// Importing dependencies
const mongoose = require("mongoose");

// Defining post schema
const userSchema = new mongoose.Schema(
  {
    name: {
      type: String,
      required: true,
      min: 6,
      max: 12,
    },
    email: {
      type: String,
      required: true,
      min: 6,
      max: 32,
    },
    password: {
      type: String,
      required: true,
      min: 6,
      max: 124,
    },
    date: {
      type: Date,
      default: Date.now,
    },
  },
  { collection: "users" }
);

module.exports = mongoose.model("User", userSchema);

```

<br>

<li>

Make a file with name **env.json**
in the root directory and add this your .gitignore

<li>Populate the JSON with the appropriate schema 
<br>

```
{
    "dbConnect": "db auth key",
    "privateKey": "string for signing jwt (HMAC SHA256 currently)"
}
```

<li>Require the package by using 
and execute the funtion you pass down a port for your local server<br>

```
const {launchServer} = require('@cyberflaw/express-mongodb-jwt');

launchServer(port);
```

<li>Hopefully it will workout
</ol>

<br/>
<h3>

[Click Here](https://www.npmjs.com/package/@cyberflaw/express-mongodb-jwt)
to visit npmjs

[Click Here](https://github.com/CyberFlaw/Express-MongoDB-JWT-Auth)
to visit the Github repo

<h2>Developer Log
<h4>
The package is still in its early stage and Im a new developer with little expreience. I'll do my best to polish out this package in the upcomming weeks. I'll be adding more features too. I've got many plans and less expriece to execute hopefully it will end up all fine.
<br>
<br>
Thanks For Your Support
