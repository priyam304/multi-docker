FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY ./ ./
CMD ["npm","run","build"]

FROM nginx
WORKDIR '/app'
COPY ./default.conf ./
COPY --from=0 /app/build ./
