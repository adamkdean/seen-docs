# docs

This documentation relates to the SEEN project. It will give you a general idea of my thoughts in the event that I don't completely finish the implementation of the project.

## Premise

Take the film/review website template provided and turn it into a working app.

## Idea

* TODO write this up properly

1. [mongodb] Start with MongoDB (plus some sort of UI for development)
2. [external dep] Find a data source to provide film/review data & assets
3. [worker] Implement a service to hydrate the data store using the aforementioned data source
4. [api] Implement an API to surface the data in MongoDB
5. [website] Implement the UI which consumes the API and renders the templates

### Optional features (if time permits)

1. Search functionality (maybe just implement a simple version?)
2. Production level robustness/logging/error handling
3. Tests for the API

### Deprioritised features (low value)

1. User authentication/profile area ("YOU" link)
2. Real historical data for film/review popularity

## Status

This will essentially be my TODO list so I can keep track of what is what.

### Done

1. [mongodb] MongoDB docker scripts
2. [external dep] API access to themoviedb.org
3. [worker] Initial film & review data store hydration
4. [worker] Resolve genres and store against film data
5. [worker] Find more film data such as director, etc

### Pending

1. [api] Implement an API to surface the data in MongoDB
2. [website] Implement the UI which consumes the API and renders the templates
