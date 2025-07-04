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

## Data Mutations

Without client side routing, the browser will serialize the form's data automatically and send it to the server as the request body for POST, and as URLSearchParams for GET. Remix does the same thing, except instead of sending the request to the server, it uses client side routing and sends it to the route's action function.

## Creating Contacts

👉 Export an action function from app/root.tsx

## Updating Data

## Updating Contacts with FormData

The edit route we just created already renders a form. All we need to do is add the action function. Remix will serialize the form, POST it with fetch, and automatically revalidate all the data.

## Redirecting new records to the edit page

```
// existing imports
import { redirect } from "@remix-run/node";
// existing imports

export const action = async () => {
  const contact = await createEmptyContact();
  return redirect(`/contacts/${contact.id}/edit`);
};
```

## Active Link Styling

## Global Pending UI

## Deleting Records

## Index Routes

## Cancel Button

useNavigate

## URLSearchParams and GET Submissions
