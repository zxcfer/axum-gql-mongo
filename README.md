# Rust graphql service boilerplate

* TODO: move to axum

### Usage

Seed some data with...
```
cargo run --bin seed
```

Run the server with...
```
cargo run
```

And then test at:
```
http://localhost:8080/graphiql
```

#### Sample query for pets
```
{
  allPets(limit:4){
    pageInfo{
      startCursor
      nextCursor
      hasPreviousPage
      hasNextPage
    }
    pets{
      name
      id
      age
      petType
      gender
      owner{
        id
        username
      }
    }
    totalCount
  }
}
```

#### Sample query for owners
```
{
  allOwners {
    pageInfo {
      startCursor
      nextCursor
    }
    owners {
      id
      firstName
      lastName
      pets {
        id
        name
      }
    }
  }
}
```

