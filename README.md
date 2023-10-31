# YuanpengShop

An eCommerce platform built with the MERN stack & Redux.

## App Demo

<img src="uploads/demo.gif" width="700"/>

## Architecture Diagram

**Frontend**: React.js (HTML, CSS, JavaScript), Redux, Material UI

**Backend**: Node.js, Express, MongoDB, JWT

## MERN stack

MERN stands for MongoDB, Express, React, Node, after the four key technologies that make up the stack.

- MongoDB — document database
- Express(.js) — Node.js web framework
- React(.js) — a client-side JavaScript framework
- Node(.js) — the premier JavaScript web server

Express and Node make up the middle (application) tier. Express.js is a server-side web framework, and Node.js is the popular and powerful JavaScript server platform. Regardless of which variant you choose, ME(RVA)N is the ideal approach to working with JavaScript and JSON, all the way through.

<img src="uploads/mern.png" width="520" height="320"/>

## React

React is a JavaScript library created by Facebook.

React is a User Interface (UI) library and is a tool for building UI components.

<img src="uploads/react_figure.png" width="520" height="320"/>

## Redux

Redux is a pattern and library for managing and updating application state, using events called "actions". It serves as a centralized store for state that needs to be used across your entire application, with rules ensuring that the state can only be updated in a predictable fashion.

- State, the source of truth that drives our app
- View, a declarative description of the UI based on the current state
- Action, the events that occur in the app based on user input, and trigger updates in the state. Actions are plain JavaScript objects that must have: 1. A type property to indicate the type of action to be carried out 2. A payload object that contains the information that should be used to change the state. Here’s an example of an action:
  ```
  const addAction = { 
    type: "INCREMENT",
    payload: {
      incrementBy: 5,
    }
  }
  ```
- Action creator, is a function that creates and returns an action object. And here is an example of an action creator. It is just a helper function that returns the action:
  ```
  const getIncrementAction = (numberToIncrement) => {
    return {
      type: "INCREMENT",
      payload: {
        incrementBy: numberToIncrement,
      }
    }
  }
  ```
- Dispatch, the Redux store has a method called dispatch. The only way to update the state is to call ``` store.dispatch()```  and pass in an action object. The store will run its reducer function and save the new state value inside, and we can call ``` getState() ``` to retrieve the updated value. We can read data from the store with ``` useSelector ```
- Reducer, is a function that receives the current state and an action object, decides how to update the state if necessary, and returns the new state. You can think of a reducer as an event listener which handles events based on the received action (event) type. Here is an example of how reducers work in Redux:
  ```
  const CounterReducer = (state = initialState, action) => {
      switch (action.type) {
        // This reducer handles any action with type "LOGIN"
        case "INCREMENT":
            return state + action.incrementBy ? action.incrementBy : 1
        case "DECREMENT":
            return state + action.decrementBy ? action.decrementBy : 1
        default:
            return state
        } 
  }
  ```
- Store, the current Redux application state lives in an object called the store. The store is created by passing in a reducer and has a method called getState that returns the current state value.
  ```
  const store = Redux.createStore(reducer)
  ```
- Selectors, are functions that know how to extract specific pieces of information from a store state value. As an application grows bigger, this can help avoid repeating logic as different parts of the app need to read the same data.

<img src="uploads/redux.png" width="510" height="290"/>


## Node.js


## JWT

JWT, or JSON Web Token, is an open standard used to share information between two parties securely — a client and a server. In most cases, it’s an encoded JSON containing a set of claims and a signature. It’s usually used in the context of other authentication mechanisms like OAuth, OpenID and microservice architecture to share user-related information.

JWT authentication is a token-based stateless authentication mechanism. It is popularly used as a client-side-based stateless session, this means the server doesn’t have to completely rely on a data store (or) database to save session information. JWTs can be encrypted, but they are typically encoded & signed.  We will be focusing on Signed JWTs. The purpose of Signed JWT is not to hide the data but to ensure the authenticity of the data. And that is why it’s highly recommended to use HTTPS with Signed JWTs.

<img src="uploads/jwt.jpg" width="525" height="300"/>

## Features

- Full featured shopping cart
- Product reviews and ratings
- Top products carousel
- Product pagination
- Product search feature
- User profile with orders
- Admin product management
- Admin user management
- Admin Order details page
- Mark orders as delivered option
- Checkout process (shipping, payment method, etc)
- PayPal / credit card integration
- Database seeder (products & users)

### ES Modules in Node

We use ECMAScript Modules in the backend in this project. Be sure to have at least Node v14.6+ or you will need to add the "--experimental-modules" flag.

Also, when importing a file (not a package), be sure to add .js at the end or you will get a "module not found" error

You can also install and setup Babel if you would like

## Usage

- Create a MongoDB database and obtain your `MongoDB URI` - [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/register)
- Create a PayPal account and obtain your `Client ID` - [PayPal Developer](https://developer.paypal.com/)
- Render: Cloud Application Hosting for Developers - [Render.com](https://render.com)

### Env Variables

Create a .env file in then root and add the following

```
NODE_ENV = development
PORT = 5000
MONGO_URI = your mongodb uri
JWT_SECRET = 'abc123'
PAYPAL_CLIENT_ID = your paypal client id

Change the values to what you want
```

## Available Scripts

In the project directory, you can run:

### Install Dependencies (frontend & backend)

```
npm install
cd frontend
npm install
```

### Run

```
# Run frontend (:3000) & backend (:5000)
npm run dev

# Run backend only
npm run server
```

## Build & Deploy

```
# Create frontend prod build
cd frontend
npm run build
```

There is a Heroku postbuild script, so if you push to Heroku, no need to build manually for deployment to Heroku

### Seed Database

You can use the following commands to seed the database with some sample users and products as well as destroy all data

```
# Import data
npm run data:import

# Destroy data
npm run data:destroy
```

```
Sample User Logins

admin@example.com (Admin)
123456

john@example.com (Customer)
123456

jane@example.com (Customer)
123456
```
