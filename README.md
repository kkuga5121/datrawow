# DataWoW Assignment in Full-stack developer (Next.js - NestJS)

This repository contains a Next.js and NestJS application for Board Application. This document provides instructions on how to set up and run the application locally.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- [Node.js](https://nodejs.org/) (version 12.22.0 or later)
- [npm](https://www.npmjs.com/) (comes with Node.js) or [Yarn](https://yarnpkg.com/)

## Installation Front-End Next.JS

Follow these steps to install the application:

1. **Navigate to the project directory**:

   ```bash
   cd board/front-end-nestjs
   ```

2. **Install the dependencies**:

   You can use either npm or Yarn. Choose one of the following commands:

   Using npm:

   ```bash
   npm install
   ```

   Using Yarn:

   ```bash
   yarn install
   ```

## Installation Back-End Next.JS

1. **Navigate to the project directory**:

   ```bash
   cd board/back-end-nestjs
   ```

2. **Install the dependencies**:

   You can use either npm or Yarn. Choose one of the following commands:

   Using npm:

   ```bash
   npm install
   ```

   Using Yarn:

   ```bash
   yarn install
   ```

3. **Set up your PostgreSQL database**:

   - Create a new PostgreSQL database.
   - Update the database connection string in the `.env` file:

     ```env
     DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/DB_NAME?schema=public"
     ```

   Replace `USER`, `PASSWORD`, and `DB_NAME` with your PostgreSQL credentials and database name.

4. **Run Prisma migrations**:

   ```bash
   npx prisma migrate dev --name init
   ```

   This command will create the necessary tables in your database based on your Prisma schema.

## Running the Application Front-End

To start the development server, run the following command:

```bash
npm run dev
```

or 

```bash
yarn dev
```

This will start the server at `http://localhost:3001`. You can open this URL in your web browser to view the application.


## Running the Application Back-End

To start the development server, run the following command:

```bash
npm run start
```

or 

```bash
yarn start
```

This will start the server at `http://localhost:3000`. You can open this URL in your web browser to view the application.

## API Documentation

This application uses [Swagger](https://swagger.io/) for API documentation. You can access the interactive API documentation by navigating to `http://localhost:3000/apitest` in your web browser after starting the server. This interface allows you to explore the available endpoints, view request and response formats, and test the API directly from the browser.
๊
## Application Back-End Disgin

# Database
![plot](./img/Diagram.png)

# API endpoints
Create Module of API to support each table.
These endpoints allow you to handle Stripe subscriptions for Publish and Analyze.

1. **Blog**
`POST Create Blog` [/api/blog]<br/>
`GET Fetch Blog` [/api/blog?page=1&limit=10]<br/>
`GET Fetch Blogs with community` [/api/blog?tag=FOOD&page=1&limit=10]<br/>
`GET Fetch Blogs of User id` [/api/blog/{userId}/user?&page=1&limit=10]<br/>
`GET Fetch Blogs of User id with community` [/api/blog/{userId}/user?tag=FOOD&page=1&limit=10]<br/>
`GET Fetch Blog by id` [/api/blog/{id}]<br/>
`PATCH Update Blog by id` [/api/blog/{id}]<br/>
`DELETE Delete Blog by id` [/api/blog/{id}]<br/>

2. **User**
`POST Create User` [/api/user]<br/>
`GET Fetch Users` [/api/user]<br/>
`GET Fetch User by username` [/api/user/{user}/username]<br/>
`GET Fetch User by id` [/api/user/{id}]<br/>
`PATCH Update User by id` [/api/user/{id}]<br/>
`DELETE Delete User by id` [/api/user/{id}]<br/>

3. **Comment**
`POST Create Comment` [/api/comment]<br/>
`GET Fetch Comments` [/api/comment]<br/>
`GET Fetch Comment by Blog Id` [/api/comment/{blogId}/blog]<br/>
`GET Fetch Comment by id` [/api/comment/{id}]<br/>
`PATCH Update Comment by id` [/api/comment/{id}]<br/>
`DELETE Delete Comment by id` [/api/comment/{id}]<br/>

ention any integrations (e.g., with other APIs or services).

# Technologies

- **NestJS**: The framework used for building the application.
- **TypeScript**: The programming language used.
- **Prisma**: The ORM used for database interactions.
- **PostgreSQL/MySQL/MongoDB**: Specify the database you're using.

## Application Front-End Disgin

# Description
1. **Blogs page**
   Design the page to include a search bar that utilizes Fuse.js for efficient search functionality, enabling users to find blogs with optional community filters.
   Include a "Create +" button for adding new blogs, which should be accessible only to signed-in users.
   Each blog should be clickable, leading to a full page view for detailed content. Additionally, the blog owner should have the ability to edit and delete their posts.
2. **Blog Full**
   Design the page to display the full content of the blog along with associated comments. Include an "Add Comment" button that allows signed-in users to submit new comments. 
   The blog owner should have the ability to edit and delete their posts, while comment owners should be able to edit and delete their own comments.
   In mobile view, the "Add Comment" text field should be displayed in a dialog.

# Description Additional
1. **Blogs page**
   ![plot](./img/loadmore.PNG)
   Design the page to include a "Load More" button for fetching additional blog data, utilizing a pagination search style to optimize page load performance.
2. **Side Bar**
   ![plot](./img/sidebar.PNG)
   Create a mobile-friendly sidebar that includes "Sign In" and "Sign Out" buttons for user login functionality.
2. **Top Bar**
   ![plot](./img/topbar.PNG)
   Add a "Sign Out" option in the user profile section of the top bar, enabling users to log out with a single click.

# Technologies

- **Next.js**: The React framework used for building the front-end application.
- **Redux**: The state management library for managing application state.
- **Redux Persist**: A library to persist and rehydrate Redux state across sessions.
- **Tailwind CSS**: A utility-first CSS framework for styling the application.
- **Fuse.js**: A lightweight fuzzy-search library for implementing search functionality.
- **TypeScript**: The programming language used for developing the application.

## Application Testing

# Back-End Running Tests

To ensure the quality and functionality of your NestJS application, you can run the test suite using the following command:

```bash
npm run test
```

# Running the Seed Script

To create sample data for your application, such as users, blogs, and comments.
Once your seed file is set up, you can run the seed script with the following command:

```bash
npm run seed
```

# View Database 

To view and manage the seeded data in your database, you can use Prisma Studio. 
Run the following command to open the Prisma Studio interface:

```bash
npx prisma studio
```
