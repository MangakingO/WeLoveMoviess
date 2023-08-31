# Project: WeLoveMovies
<img src="images/screenshot.png" alt="Project Screenshot" width="600">

## Setup and Deployment Guide

Follow these steps to set up and deploy the WeLoveMovies project on your local machine and on the Render platform.

### 1. Fork the Repository

1. Fork the WeLoveMovies repository on GitHub to your own GitHub account.

### 2. Install Dependencies

1. Clone the forked repository to your local machine.
2. Open your terminal and navigate to the project directory.
3. Run the following command to install project dependencies:

 ```sh
   npm install
   ```

### 3. Set Up Database and Migrations

1. Make sure Knex is installed globally. If not, you can install it using:


 ```sh
   npm install -g knex
   ```

2. Create a `.env` file in the root directory of the project. Add the following line, replacing `<YOUR_DATABASE_URL>` with your actual ElephantSQL database URL: DATABASE_URL=<YOUR_DATABASE_URL>


3. Run the migration command to set up the database tables:

 ```sh
   npx knex migrate:latest
   ```


4. Seed the database with initial data:
```sh
  npx knex seed:run
  ```


### 4. Deploy Backend on Render

1. Create an account on Render (if you don't have one).
2. Log in to Render and click "Add a New Web Service."
3. Choose a name for your backend service.
4. For the "Build Command," use:

```sh
  node src/server.js
  ```

6. Add an environmental variable with the key `DATABASE_URL` and the value as your ElephantSQL database URL.

7. Deploy the service.

### 5. Connect Backend and Frontend on Render

1. Follow the link provided above to access the frontend repository.

2. Create a `.env.production` file in the frontend project's root directory.

3. Add the following line to the `.env.production` file, replacing `<BACKEND_RENDER_URL>` with the URL of your backend service on Render: REACT_APP_API_URL=<BACKEND_RENDER_URL>

4. Navigate to `src/utils/api.js` in the frontend project.

5. Replace the value of `API_BASE_URL` with your backend Render URL:
const API_BASE_URL = "<BACKEND_RENDER_URL>";


### 6. Deploy Frontend on Render

1. Go back to your Render account dashboard.
2. Click "Add a New Web Service" again.
3. Choose a name for your frontend service.
4. For the "Build Command," use:

```sh
  npm install
  ```
5. For the "Start Command," use:

```sh
  npm start
  ```

6. Deploy the Service.

# Project Links

- **Frontend Render:** [Render](https://frontendwelovemovies.onrender.com/)
  This is the deployed frontend connected to the backend.

- **Backend Render:** [Render](https://backendwelovemovies.onrender.com/)
  This is the deployed backend.

- **Frontend GitHub Repository:** [GitHub](https://github.com/MangakingO/starter-movie-front-end)
  This is the link to the GitHub repository for the frontend code.
