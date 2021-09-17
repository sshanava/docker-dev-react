To run container with volumes:
docker run -it -p 3000:3000 -v /app/node_modules -v $(pwd):/app <image id/tag>



React App Exited With Code 0
Recently, a bug was introduced with the latest Create React App version that is causing the React app to exit when starting with Docker Compose.

To Resolve this:

Add stdin_open property to your docker-compose.yml file

 web:
    stdin_open: true

Make sure you rebuild your containers after making this change with  docker-compose down && docker-compose up --build
