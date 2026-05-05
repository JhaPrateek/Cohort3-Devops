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
