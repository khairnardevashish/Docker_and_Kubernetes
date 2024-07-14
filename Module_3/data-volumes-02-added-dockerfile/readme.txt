# Setting up env variable (PORT) via docker run
docker run --rm -p 3000:7000 -e PORT=8000 -d -v feedback:/app/feedback -v $(pwd):/app:ro -v /app/temp -v /app/node_modules --name feedback-app  node-feedback:env

# Setting up env variable (PORT) via docker .env file
docker run --rm -p 3000:7000 --env-file ./.env -d -v feedback:/app/feedback -v $(pwd):/app:ro -v /app/temp -v /app/node_modules --name feedback-app  node-feedback:env  

# We can use ARG to set up env variables which can be modified. For example we can handle the default value of port while we build image
# In Dockerfile
    ARG DEFAULT_PORT=80
    ENV PORT=$DEFAULT_PORT
    EXPOSE $PORT

docker build -t node-feedback:dev --build-arg DEFAULT_PORT=8000 .
