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

## The Contact Route UI

👉 Create the app/routes directory and contact route module

```
mkdir app/routes
touch app/routes/contacts.\$contactId.tsx
```

In the Remix route file convention, . will create a / in the URL and $ makes a segment dynamic. We just created a route that will match URLs that look like this:

    /contacts/123
    /contacts/abc

👉 Add the contact component UI

```cmd
app/routes/contacts.$contactId.tsx
```

## Client Side Routing

👉 Change the sidebar <a href> to <Link to>

## Nested Routes and Outlets

👉 Render an <Outlet />

## Loading Data

👉 Export a loader function from app/root.tsx and render the data

```
 const { contacts } = useLoaderData();
```

## Type Inference

```
const { contacts } = useLoaderData<typeof loader>();
```

## URL Params in Loaders

👉 Click on one of the sidebar links

```
const contact = await getContact(params.contactId);
```

## Validating Params and Throwing Responses

