# VideoStreamingSite

This is yet another application that goes along with "Modern React with Redux" from Udemy. Here are some notes I took along the way

#### App Challenges

- Need to be able to navigate around to separate pages in our app
- Need to allow a user to login/logout (oAuth)
- Need to handle forms in Redux
- Need to master CRUD (Create Read Update Delete) operations in React/Redux
- Errors will likely occur.. need good error handling

#### Bad Navigation

- You add an <a/> tag to your application with href='pagetwo' and click it
- Your browser makes a request to localhost:3000
- Development server responds with index.html file
- Browser receives index.html file, dumps old HTML file it was showing (including all of your React/Redux state data!)
- index.html file lists our JS files in script tags - browser downloads and executes these scripts
- app starts up

#### What We Want With Routing

- User wants to navigate to another page in our app
- User clicks a 'Link' tag
- React Router prevents the browser from navigating to the new page and fetching new index.html file
  URL still changes
  'History' sees updated URL, takes URL and sends it to BrowserRouter
- BrowserRouter communicates the URL to Route components
- Route components rerender to show new set of components

#### Different types of routers

- BrowserRouter -> localhost:3000/pagetwo
  - Users everything after the TLD (.com, net) or port as the 'path'
- HashRouter -> localhost:3000/#/pagetwo
  - Uses everything after a # as the 'path'
- MemoryRouter -> localhost:3000/
  - Doesn't use the URL to track navigation

#### OAuth Authentication

- User authenticates with outside service provider
- User authorizes our app to access their information
- Outside provider tells us about the user
- We are trusting the outside provider to correctly handle identification of the user
- OAuth can be used for (1) user identification in our app and (2) our app making actions on behalf of user
