# GraphQL Basic Implementation

## Tryout

Query

```JSON
query {
  getContacts {
    firstName
    lastName
    email
    company
  }
}
```

Mutation

```JSON
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

```JSON
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

```JSON
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

```JSON
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