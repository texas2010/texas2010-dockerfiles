FROM node:lts

ENV TEST_KIND=integration

WORKDIR /apps/backend-project/
RUN npm install --global fastify-cli
RUN fastify generate . --esm --lang=typescript --integrate
RUN npm install

WORKDIR /apps/frontend-project/
RUN npm create vite@latest . -- --template react-ts
RUN npm install

WORKDIR /apps/base

RUN npx playwright install --with-deps