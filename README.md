# Mern Authentication Starter Pack

## Designed with

- React with Typescript Frontend
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
