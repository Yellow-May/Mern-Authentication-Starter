# Mern Authentication Starter Pack

## Designed with

- React with Typescript and React Router v6 Frontend
- Nodejs Backend with MongoDB

## Frontend

- Designed with [Antd](https://ant.design/), featured with various form validations for login and registration
- State management handle by [Redux Toolkit](https://redux-toolkit.js.org/)
- [Axios](https://www.axios.com/) to handle request to the backend along with interceptors to handle the refresh token request when access token expires

## Backend

- APIs for login, registration, request refresh token, logout, get user info and more

## Authentication Principle

Uses [JWT](https://www.npmjs.com/package/jsonwebtoken?msclkid=1b172e6bd04711ec842b21e05d274812) to create access and refresh token for authentication.
Access token is sent to the frontend on login, registration and refreshing of token, while refresh token is store in a httpOnly cookie in the client.
The refresh token is saved to a DB along with the user info and a unique browser ID that allows for signing in on various devices.
When access token expires, send a request to the refresh API and retreive a new access token.
Access tokens are short lived, while refresh tokens are less.
Brower Ids are long lived and hold no valuable information.

## Environment variables

### Client side

REACT_APP_BACKEND_URL = local backend url
Examples

- dev : 'http://localhost:5000/api' or 'http://localhost:5000'
- prod : '/api' or '/'

REACT_APP_PERSIST = a random string name to store your PERSIST boolean in local storage
Example : ewhou838u489u508

### Server side

NODE_ENV = 'development' or 'dev' **not required in production**
MONGO_URI = mongo db uri
PORT = port number **not required in production**

JWT_ACCESS_SECRET = random long string preferrable use crypto to generate one
JWT_REFRESH_SECRET = same as above
REFRESH_COOKIE_NAME = random string just like REACT_APP_PERSIST
BROWSER_COOKIE_NAME = same as above
