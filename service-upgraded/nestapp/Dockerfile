FROM node:22.21.1-alpine3.21

LABEL OWNER="NUR"
LABEL PROJECT="DIPLOMADO CONTENERIZACION DE APLICACIONES"
LABEL MAINTAINER="Edurdo Flores"

ARG VERSION="2.5.1"

ENV CONFIG_FILE_PATH=/app/config
ENV API_VERSION=v2
ENV ENVIRONMENT=development

WORKDIR /app

COPY package.json package.json
COPY yarn.lock yarn.lock

RUN npm install @nestjs/cli && npm install

COPY . .

EXPOSE 3000

VOLUME [ "/uploads" ]

#USER rest_api_user

RUN npm run build

HEALTHCHECK --interval=1m --timeout=5s CMD curl -f http://localhost:3000/prueba || exit 1

CMD ["node", "dist/main.js"]
