FROM alpine:latest
ARG NEW_RELIC_LICENSE_KEY
ENV NEW_RELIC_APP_NAME=app01
ENV NEW_RELIC_DISTRIBUTED_TRACING_ENABLED=true
ENV NEW_RELIC_LICENSE_KEY=$NEW_RELIC_LICENSE_KEY
ENV NEW_RELIC_APPLICATION_LOGGING_ENABLED=true
ENV NEW_RELIC_APPLICATION_LOGGING_METRICS_ENABLED=true
ENV NEW_RELIC_LOG_LEVEL=trace

RUN apk add --no-cache nodejs npm

WORKDIR /app
COPY package.json /app
RUN npm install

COPY . /app

EXPOSE 3000
CMD ["npm", "start"]
