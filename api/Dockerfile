# SpotESIfy API — Dockerfile
FROM node:20-alpine
RUN apk add --no-cache curl
WORKDIR /app

COPY package*.json ./

RUN npm install --only=production

COPY . .

USER node

HEALTHCHECK --interval=30s --timeout=5s --start-period=10s --retries=3 \
  CMD curl -f http://localhost:5000/health || exit 1

CMD ["node", "index.js"]
