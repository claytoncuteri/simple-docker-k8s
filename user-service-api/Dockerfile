# each step creates a layer

FROM node:alpine
WORKDIR /app
ADD package*.json ./
# by putting package here, we can leverage cacheing to reduce docker image build time
# the key is to think about what will change and take advantage of cacheing when possible
RUN npm install
ADD . .
# because ADD is likely to change, it is best to put it towards the end to leverage cacheing
CMD ["node", "index.js"]

# we have written a docker image for the user-service-api written with node and express js