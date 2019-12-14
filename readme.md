# GraphQL Basic Implementation

## Tryout

Query

```gql
query {
  getContacts {
    firstName
    lastName
    email
    company
  }
}
```

Create Mutation

```gql
mutation {
  createContact( input:{
    firstName: "Rahul",
    lastName: "Jain",
    email: "rahulnlb@gmail.com",
    company: "SAP"
  }) {
    id
    firstName
  }
}
```

Get one contact

```gql
query{
  getOneContact(id:"5df4b8b99c57c169f416f727") {
    firstName
    lastName
    company
    email
  }
}
```

Alias

```gql
query{
  one: getOneContact(id:"5df4b8b99c57c169f416f727") {
    firstName
    lastName
    company
  }
  
  two : getOneContact(id:"5df4b8b99c57c169f416f727") {
    firstName
    lastName
  }
  
}
```

Fragments

```gql
query{
  one: getOneContact(id:"5df4b8b99c57c169f416f727") {
    ...contactFragment
  }
  
  two : getOneContact(id:"5df4b8b99c57c169f416f727") {
    ...contactFragment
  }
  
}

fragment contactFragment on Contact {
  firstName
  lastName
  email
}
```

Update Mutation

```gql
mutation {
  updateContact(input: {
    id: "5df4b61204e3703da8fe3607"
    firstName: "Deepanshi"
    lastName: "Katoch"
    company: "SAP"
  }) {
    firstName
    lastName
    email
    company
  }
}
```
