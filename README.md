# GraphQL
[GraphQL Explorer](https://docs.github.com/en/graphql/overview/explorer)

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

#Schema

### Types: Int | Float | String | Boolean | ID

```ts
type Author {
  id: ID;
  firstName: string;
  rating: Float;
  numOfCourses: Int
}

enum Language {
  ENGLISH
  HEBREW
  SPANISH
}

```
#Query and Mutation Types
#### Query is an entery point for the service request
#### Mutation is the object data that can be mutate. (add, delete)

```ts
  schema {
    query:Query
    mutation: Mutation
  }
```

#Demo

```ts 
    {
      viewer {
        login
        name
      }
    }
    
  ### Returned data:
  
  {
  "data": {
    "viewer": {
      "login": "avishai84",
      "name": null
    }
  }
}
```
### GraphQL Query example:
##### This query consists of three components:
```ts
    query GetAllFilms { // GetallFilms is the operation name that clients can set. This can be useful for debugging issues.
      allFilms { // allFilms is field exposed endpoint on the root node. It is a complex types of Film that combines several scalar values into a single unit.
      // allFilms is also a field that combines the fields nested inside it.
        films {
          title // title, episodeID, director, etc. are fields.
          episodeID // These are units of data that you are requesting to appear in the response data. 
          openingCrawl
          director
          producers
          releaseDate
        }
      }
    }
    
```
