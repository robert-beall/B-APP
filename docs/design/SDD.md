# Software Design Document
This document outlines the chosen platforms and languages used for each part of the application stack. 

The overarching design principle for this project is *simplicity*. Each component should be simple, well-documented, and fully understood.

The application stack is as follows:
- Database
- Backend
- Frontend
- CI/CD
- Deployment

## Database
[*PostgreSQL*](https://www.postgresql.org/) will be used for the database due to its wide adoption in modern industry and useful features. 

### Security
Passwords will be encrypted using the [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) algorithm. Passwords will be hashed with a salt directly in postgresql. This comes with the advantage of the salt being automatically stored. All password hash comparisons will be performed on the database side as well. 

## Backend
[*NodeJS*](https://nodejs.org/en) will be used for the backend API, due to its relative simplicity. The following will be used for the backend:

### Web Server
[*Express*](https://expressjs.com/) will be used due to its widespread use in node-based APIs and its ease of use. 

### ORM 
The [*Prisma*](https://www.prisma.io/orm) ORM will be used for database connections. This is due to its relative simplicity and growing use in modern NodeJS applications. 

### Testing
[*Jest*](https://jestjs.io/) will be used for testing.

### Linting and Type Safety
[*Typescript*](https://www.typescriptlang.org/) will be used to help ensure code consistency and quality. 

[*ESLint*](https://eslint.org/) and [*Prettier*](https://prettier.io/) will be used for linting and formatting. The pairing of these two dependencies seems to be a standard in the industry. 

## Frontend
The frontend will use the [React](https://react.dev/) framework. The following is an overview of technologies used:

### Platform
[NextJS](https://nextjs.org/) will be used as the platform, providing simple routing and an intuitive structure.

### Testing
[*Jest*](https://jestjs.io/) will be used in conjunction with [React Testing Environment](https://testing-library.com/docs/react-testing-library/intro/). This will combine the test runner of Jest with the ability to test React components from the user perspective. 

### Linting and Type Safety
Like with the [backend](#linting-and-type-safety), ESLint and Typescript will be used. The frontend will use the [ESLint React Plugin](https://github.com/jsx-eslint/eslint-plugin-react) to extend ESLint.

### Authorization
[JSON Web Tokens (JWT)](https://jwt.io/introduction) will be used for authorization.

## CI/CD

### Hosting
The application will be hosted on [Amazon Web Services (AWS)](https://aws.amazon.com) cloud, due to its wide adoption as a platform. Additionally, I have experience working with AWS.

### Pipeline
The pipeline will use [Jenkins](https://www.jenkins.io/) for its widespread adoption and relative ease of use. The pipeline will conduct linting, unit tests, and a sonarqube scan on each branch and deploy the `main` branch to AWS. A [Terraform](https://developer.hashicorp.com/terraform) script will be used for final deployment and for building out AWS resources.