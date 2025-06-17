# STEPS

## Setup

👉 Generate a basic template

```
npx create-remix@latest --template remix-run/remix/templates/remix-tutorial
```

👉 Adding Stylesheets with links
```
import type { LinksFunction } from "@remix-run/node";
// existing imports

import appStylesHref from "./app.css?url";

export const links: LinksFunction = () => [
  { rel: "stylesheet", href: appStylesHref },
];
```
