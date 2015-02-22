# OpenBrain Live Stream Data
This allows for live control of an openBrain setup using nodejs.

## Starting

```
npm install openbrain --save
```

Initialize the OpenBrain object
```
var OpenBrain = require('openBrain');
var myBrain = new OpenBrain('https://<your-brain>.openbrain.com');
```

## Using

```
// Init new session
var session = myBrain.createSession({
  name: <name>,
  activity: <activity>  
});

// Begin Recording
session.startRecording();

// Add annotation
session.addAnnotation('<annotation>');

// Stop Recording
session.stopRecording();
```
# OpenBrain Stored Data
This is for building client-side webapps with previously stored sessions. Users must approve web app use of their data through oauth.

## Starting

Run this in your web project
```
bower install openbrain --save
```

Add this to your HTML
```
<script src="bower_components/openbrain/dist/openbrain.min.js" type="text/javascript"></script>
```

Initialize the OpenBrain object
```
var myBrain = new OpenBrain('https://<your-brain>.openbrain.com');
```

## Using

```
// Retrieving Users
var user = myBrain.getUser('<user-id>');

// Retrieving Applications
var application = user.getApplication('<application-id>');

// Retrieving Sessions
var session = application.getSession('<session-id>');
// OR
var session = user.getSession('<session-id>');

// Retrieving Channels
var channel = application.getChannel('<channel-id>');
```

