# geoblink-search

> Vue.js is an approachable, versatile and performant framework that helps to create a more maintainable code base.
> To build this very small application I decided to use Vue because it has a very small learning curve and it is very easy to get a good understanding of the basic concepts; but most importantly, writing code in Vue is very enjoyable.

## Application features

* Responsive design
* Ajax calls
* Dropdown with support for filtering
* Dropdown with support for selecting multiple items

## Libraries

* vue-router
* vue-resource
* vue-select
* bootstrap

## Clone and set up project

``` bash
# Clone project
https://github.com/loris-fo/geoblink-search.git
cd geoblink-search

# Install dependencies
npm install
```

## add & start fake server

``` bash
# Install json-server globally to fake the Node.js backend
npm install -g json-server

# Run the fake server at localhost:3000
json-server --watch src/db.json
```

## Start application

``` bash
# serve with hot reload at localhost:8080
npm run dev
```
