```gql
#=======================
#Schema:
#=======================
type Author {
  name: String
  id: ID!
  posts: [Post!]!
}

type Post {
  title: String!
  content: String! 
  author: Author!
  likes: Int!
}


type Query {
  posts: [Post!]!
  author(id: ID!): Author
  post(id: ID!): Post
}



type PostInput {
  title: String!
  content: String!
  authorId: ID!
}

type AuthorInput {
  name: String!
}

type Mutation {
  createPost($post: PostInput!): Post!
  createAuthor($author: AuthorInput!): Author!
}

enum Direction {
 LTR
 RTL
}


#========================
#Client :
#========================

Fragment postFields on Post {
  title
  content
  author  {
    name
  } 
  likes
}

query posts {
  post(id: "e75374d8") {
   ...postFields
  }
}
```

Graphql Concepts & Terms:
https://daily.dev/blog/graphql-terminology-cheatsheet


