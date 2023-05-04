# GraphQL

## GraphQL query language for your API

## GQL let you write a query to get on that response, 

```json
example GQL request

{
  allPeople(last:3){
    People {
    name
    gender
    }
  }
}

```

# Core Concepts:

REST vs. GQL

#### In REST API you need an end point for each query, for example

##### In this example, each REST endpoint will provide part of the data you will need to view this object:
Display author, courses,rating:

```js

/author/<id>/author <-----------> FETCH DATABASE
/courses/<id>/courses <-----------> FETCH DATABASE
/rating/<id>/rating <-----------> FETCH DATABASE
/topics/<id>/topics <-----------> FETCH DATABASE

```

#### IN this example, GQL get a single request and return JSON with the data just as requested. (No extra data will be return)

```js
Query:
/author/<id>/{author + courses + rating + topics}  <-----------> FETCH DATABASE

Example GQL query:

{
author (id: 100) { // asking for the author info with passing an ID
  name // request their name
  courses {  // request their courses
    title // request their title
    }
   rating  // request their rating
   topics (last : 3){ // request their topics with only last 3 responses
      name
    }
  }
}

```

