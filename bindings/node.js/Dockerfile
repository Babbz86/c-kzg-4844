FROM node:22.7-alpine
RUN apk update && apk add --no-cache g++ make python3

WORKDIR /app/bindings/node.js

COPY dist .
RUN yarn install

COPY test ./test
COPY jest.config.js .
COPY ref-tests ../../tests
CMD ["yarn", "jest"]
