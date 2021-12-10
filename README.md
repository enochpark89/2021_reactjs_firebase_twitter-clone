# Twitter-Clone


# Development

1. Install reactjs.
2. Use Google Firebase.
    a. Login 
    b. Create a project
    c. Create a web app
    - Google provide instruction on implementing Firebase to your app using JavaScript.
    - There are better way if you click javascript react
    ```js
    npm install --save firebase
    ```
    *Please refer to the link: https://www.npmjs.com/package/firebase*    

3. Create firebase.js that contains firebase config

```js
import * as firebase from "firebase/app";
// Your web app's Firebase configuration
const firebaseConfig = {
  // .....(hidden but givien by Google)
  };

  // initialize firebase

export default firebase.initializeApp(firebaseConfig);
```

4. import firebase.js from index.js
```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import firebase from './firebase';
// you can view firebase object from the console if imported successfully.
console.log(firebase);

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);


```

# 2. Secure keys

- If you put the API keys and sensitive information, it is better to put it in .env. 
- This is not a security, when people run reactjs, it actually access the keys. This is only hiding from Github. 
- If you build in the production, create-react-app will get the keys from .env.
firebase.js
```js
const firebaseConfig = {
    apiKey: process.env.REACT_APP_API_KEY,
    authDomain: process.env.REACT_APP_AUTH_DOMAIN,
    databaseURL: process.env.REACT_APP_DATABASE_URL,
    projectId: process.env.REACT_APP_PROJECT_ID,
    storageBucket: process.env.REACT_APP_STORAGE_BUCKET,
    messagingSenderId: process.env.REACT_APP_MESSAGIN_ID,
    appId: process.env.REACT_APP_APP_ID,
  };
```

# 3. Router Set up

- Use react-router-dom to create these routes.
- Create a seperate component for Router as router.js.


Structure:

- components
-- app.js
- routes
-- Auth.js: login page
--  