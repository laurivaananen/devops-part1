Inside the backend-example-docker folder I built the image with

`
docker build -t backend-example .
`

And then run the image with

`
docker run -p 8000:8000 -d backend-example
`

Inside the frontend-example-docker folder I built the image with

`
docker build -t front-endexample .
`

`
docker run -p 5000:5000 -d frontend-example
`

After this I went to localhost:5000 and pressed Excersize 1.7: Press to Test! and it returned Working!

The dockerfiles are in the folders `backend-example-docker` and `frontend-example-docker`

Dockerfile for backend

`
FROM node
WORKDIR /workdir
COPY . .
RUN npm install
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]
`

Dockerfile for frontend

`
FROM node
WORKDIR /workdir
COPY . .
RUN npm install
EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD ["npm", "start"]
`