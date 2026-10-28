# BlogQL — GraphQL Blog

A blog built as a single-page application: a **Vue 2** front end using **Apollo Client** to query a **GraphQL** API powered by **Laravel 8** and **Lighthouse**, styled with **Tailwind CSS**.

![Laravel](https://img.shields.io/badge/Laravel-8-FF2D20?logo=laravel&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-Lighthouse-E10098?logo=graphql&logoColor=white)
![Vue](https://img.shields.io/badge/Vue-2-4FC08D?logo=vuedotjs&logoColor=white)
![Apollo](https://img.shields.io/badge/Apollo_Client-311C87?logo=apollographql&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?logo=tailwindcss&logoColor=white)

## Features

- List of all posts
- Single post page
- Posts filtered by **topic** (slug-based URLs)
- Posts filtered by **author**, with author avatars
- 404 page for unknown routes
- Schema-first GraphQL API with Lighthouse directives (`@all`, `@find`, `@paginate`, `@hasMany`, `@belongsTo`)
- GraphQL Playground and Laravel Telescope for development

## GraphQL Schema

```graphql
type Query {
  users: [User!]!            # paginated
  user(id: ID!): User
  posts: [Post!]!
  post(id: ID!): Post!
  topic(slug: String!): Topic
}

type User  { id: ID!, name: String!, email: String!, avatar: String!, posts: [Post!]! }
type Topic { id: ID!, name: String!, slug: String!, posts: [Post!]! }
type Post  { id: ID!, title: String!, lead: String!, content: String!, author: User!, topic: Topic! }
```

## Getting Started

**Prerequisites:** PHP 7.3+ / 8, Composer, Node.js, MySQL

```bash
git clone https://github.com/mostfaswaisi93/blog-ql.git
cd blog-ql
composer install
npm install && npm run dev

cp .env.example .env
php artisan key:generate
# set DB_DATABASE / DB_USERNAME / DB_PASSWORD in .env
php artisan migrate
php artisan serve      # http://localhost:8000
```

GraphQL Playground: `http://localhost:8000/graphql-playground`

## Related

- [laravello](https://github.com/mostfaswaisi93/laravello) — Trello clone with the same Laravel + Lighthouse + Vue + Apollo stack

## Author

**Mustafa T. Al-Swaisi** · [LinkedIn](https://www.linkedin.com/in/mostfaswaisi93/) · [GitHub](https://github.com/mostfaswaisi93)
