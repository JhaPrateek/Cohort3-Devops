## Steps followed

1 - Created basic Node application
2 - Added Dockerfile and .dockerignore
3 - Added node_modules in .dockerignore

4 - In Dockerfile:
    - Used base image (node:alpine)
    - Set working directory (/app)
    - Copied project files (COPY . .)
    - Installed dependencies (RUN npm install)
    - Exposed application port (EXPOSE 3000)
    - Added startup command (CMD ["node", "index.js"])

---

### Difference between RUN and CMD

- RUN:
    Executes during image build time
    Example: installing dependencies (npm install)

- CMD:
    Executes when container starts
    Example: running application (node index.js)

### Command used

- docker build -t prateek-app . -> t is tag/name
- docker run -p 3000:3000 prateek-app -> port mapping left sid is host machine port : right side is container port

### Layers 
    - Images are built layer by layer
    - Like if we bulid 2 or more container so why need to load Base image or any step which is common again and again. So it gets cached. 
    - Layers can get re-used across docker builds

### Volume 
    - docker volume create volume_database
    - docker run -v volume_database:/data/db -p 27017:27017 mongo   

