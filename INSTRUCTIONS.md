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

## Development-workflow

:

👉 Add a "scripts" entry to package.json

```
{
  "scripts": {
    "dev": "node ./server.js",
    "start": "cross-env NODE_ENV=production node ./server.js"
  }
  // ...
}
```

👉 Add Vite development middleware to your server - server.js

```
import { createRequestHandler } from "@remix-run/express";
import express from "express";

const viteDevServer =
  process.env.NODE_ENV === "production"
    ? null
    : await import("vite").then((vite) =>
        vite.createServer({
          server: { middlewareMode: true },
        })
      );

const app = express();
app.use(
  viteDevServer
    ? viteDevServer.middlewares
    : express.static("build/client")
);

const build = viteDevServer
  ? () =>
      viteDevServer.ssrLoadModule(
        "virtual:remix/server-build"
      )
  : await import("./build/server/index.js");

app.all("*", createRequestHandler({ build }));

app.listen(3000, () => {
  console.log("App listening on http://localhost:3000");
});
```

👉 Start the dev server

```
npm run dev
```
