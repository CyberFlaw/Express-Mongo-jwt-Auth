# quik-auth @0.0.1

![image info](https://img.shields.io/github/issues/CyberFlaw/json-auth)
![image info](https://img.shields.io/github/forks/CyberFlaw/json-auth)
![image info](https://img.shields.io/github/stars/CyberFlaw/json-auth)
![image info](https://img.shields.io/github/license/CyberFlaw/json-auth)

<h4>A small package which makes authentification using express-mongodb and jwt much simpler. The only effort is to build your own mongoose.Schema and set values for a few json keys. More features will be added soon...

<br/>
<br/>

<br>

<!-- <h2> How to Configure:
<h4>
<ol>
<li>

Run `npm i express mongoose jsonwebtoken`

<li>

Run `npm i json-auth`

<li>

Make a file with name **config.json**
in the root directory

<li>Populate the JSON with the appropriate schema
<br>

```
{
    "schemaPath": "path of your mongoose.Schema for your user",

    "jwt":{
            "expiresIn": "refer jwt documentation"
    }
}
```

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
const {launchServer, auth, app} = require('@cyberflaw/express-mongodb-jwt');

launchServer(port);

app.get(
  '/private/route',
  auth,
  (req,res) => res.send("Its a private route!")
);
```

<li>

`auth` is a Middleware which can be passed to your other routed in order to make it private. This will be the middleware code running in the background

```

const token = req.header("token");

  if (!token) return res.status(401).json({ message: "Auth Error" });

  try {
    const decoded = jwt.verify(token, process.env.PRIVATE_KEY);
    req.user = decoded.user;

    next();
  } catch (err) {
    console.log(err);
    res.status(500).send({ message: "Invalid Token" });
  }

```

<li>Hopefully it will workout
</ol>

<br/>
<h3>

[Click Here](https://github.com/CyberFlaw/json-auth)
to visit the Github repo

[Click Here](https://www.npmjs.com/package/json-auth)
to visit the npmjs

<br> -->

<h2>Developer Log
<h4>
The package is still in its early stage and Im a new developer with little expreience. I'll do my best to polish out this package in the upcomming weeks. I'll be adding more features too. I've got many plans and less expriece to execute hopefully it will end up all fine.
<br>
<br>
The repository is kinda a mess right now. Its not in a place to ask for contributors. I'll be fixing it soon more details on that later. Meanwhile start an Issue if you spot some bugs of errors in my code. 
<br>
<br>
❤ Thanks For Your Support ❤
