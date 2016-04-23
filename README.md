# docs

This documentation relates to the SEEN project. It will give you a general idea of my thoughts in the event that I don't completely finish the implementation of the project. It will be a working document so take a look at the history if you want a play by play.

## Premise

Take the film/review website template provided and turn it into a working app.

## Idea

My first idea is to show a full stack. I will start with the MongoDB service, then a Node.js service to hydrate this store with data. Preferably, I'd like IMDb data, but if restrictive, I'll look for an alternative. Once I have the data, I will write an API which surfaces it, and then, finally hook up the UI using the provided templates.

It would be nice to add features like search, tests, deployment scripts, and universal JavaScript if Dust.js supports it, however, given how busy my week is and how I lose `NaN` hours on Saturday to a wedding I don't even want to go to, I'll probably knock that one on the head.

Finally, I would love to get this to a point where I can deploy it to a droplet. But now it's time for a sandwich.

1. [mongodb] Start with MongoDB (plus some sort of UI for development)
2. [external dep] Find a data source to provide film/review data & assets
3. [worker] Implement a service to hydrate the data store using the aforementioned data source
4. [api] Implement an API to surface the data in MongoDB
5. [website] Implement the UI which consumes the API and renders the templates

### Optional features (if time permits)

1. Search functionality (maybe just implement a simple version?)
2. Production level robustness/logging/error handling
3. Tests for the API
4. Containerisation + deployment scripts
5. Universal JavaScript for website UI

### Deprioritised features (low value)

1. User authentication/profile area ("YOU" link)
2. Real historical data for film/review popularity

### Bonus Round (only available to working apps)

1. Deploy to Digital Ocean droplet

## Status

This will essentially be my TODO list so I can keep track of what is what.

### Done

1. [mongodb] MongoDB docker scripts
2. [external dep] API access to themoviedb.org
3. [worker] Initial film & review data store hydration
4. [worker] Resolve genres and store against film data
5. [worker] Find more film data such as director, etc
6. [api] Initial API setup using something like Hapi
7. [api] Define endpoints/tests
8. [api] Hook API up to MongoDB
9. [worker] Convert film title to slug and store in db
10. [worker] Generate mock film lengths
11. [api] Implement film-based routes
12. [api] Implement ES6 mocha tests
13. [api] Implement review-based routes
14. [website] Look into Dust.js and get example server-side rendering working
15. [website] Get initial templates rendering with mocked data
16. [website] Hook up server-side rendering to api

### In Progress

1. Deployment (brucey bonus!)

### Scrapped features

1. [website] Determine whether Dust.js supports isomorphic/universal JavaScript -- worth it for demo?
2. [website] If using universal JavaScript, hook up pass through API endpoints

## Links

[Seen Project @ Quay.io](https://quay.io/organization/seenproject)
[Server setup document](server.md)
