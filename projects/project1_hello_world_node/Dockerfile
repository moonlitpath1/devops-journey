#every instruction is considered a step/layer
# docker caches layers if nothing is changed

# node js image
FROM node:24

# tell docker to pretend it's working in app folder. all files will be created here.
WORKDIR /app

#in docker, we first install dependencies then the code, unlike normal way of first downloading code then dependencies


#install all our dependencies
COPY package*.json ./
# cpy files starting with package, ending with json
# package-lock.json
# package.json
RUN npm install


#copy all local files to current working directory
COPY . .

#my local node_modules should not be added to the image.. so we add it to .dockerignore

ENV PORT=8080
EXPOSE 8080


#there can only be 1 cmd. 
#it tells docker HOW to run the application 
CMD ["node","src/index.js"]


#RUN: shell form commands
#CMD: exec form commands -- written as strings

