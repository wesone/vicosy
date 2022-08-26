# Vicosy

Vicosy is a simple peer-2-peer video conference app.
It uses the browser's WebRTC implementation wrapped inside a [React](https://reactjs.org/) app and comes with a [Node.js](https://nodejs.org/) signaling server that is used for establishing connections and handle conference rooms.

# Getting started with Vicosy

The project is containerized with [Docker](https://www.docker.com/) to make it portable, flexible and easy to deploy. To make things easier, there are [docker-compose](https://docs.docker.com/compose/) files for the development and production environments.

## Development

To start the development environment simply use `docker-compose up`.

This will start the backend and frontend in different containers. As React has its own development server, the frontend needs to run on a different port that can be changed inside the `docker-compose.yml`.

Open [http://localhost:3001](http://localhost:3001) to view the frontend in your browser.

The frontend automatically communicates with the backend that runs on port `3000` (can also be changed inside the `docker-compose.yml` but keep in mind that it is necessary to sync the port in the `proxy` field in `frontend/package.json`).

## Production

To start a production build run `docker-compose -f docker-compose.production.yml up -d`.

The `-d` (or `--detach`) is optional and only to start the containers in the background.

In production mode there is just the backend container that will also serve the frontend. So open [http://localhost:3000](http://localhost:3000) to view the frontend in your browser.
