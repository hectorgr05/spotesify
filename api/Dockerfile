# SpotESIfy API — Dockerfile
FROM node:20-alpine
RUN apk add --no-cache curl
WORKDIR /app

COPY . .

RUN npm install

EXPOSE 5000

HEALTHCHECK --interval=10s --timeout=3s --retries=3 \
  CMD curl -f http://localhost:5000/api/health || exit 1
USER node
CMD ["npm", "start"]
