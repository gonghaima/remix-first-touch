# STEPS

## Install Remix / create an app

npx create-remix@latest

## Bring Your Own Server

👉 Install Express, the Remix Express adapter, and cross-env for running in production mode

```
npm i express@4 @remix-run/express cross-env

# not going to use this anymore
npm uninstall @remix-run/serve
```

👉 Create an Express server
```
touch server.js
```

👉 Run your app with express
```
node server.js
```
debug
```
node --inspect server.js
```
