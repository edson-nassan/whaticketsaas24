FROM node:20-alpine
RUN apk add --no-cache git wget python3 make g++ chromium
ENV PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true \
    PUPPETEER_EXECUTABLE_PATH=/usr/bin/chromium-browser
WORKDIR /app
COPY backend/package*.json ./
RUN npm install --legacy-peer-deps
COPY backend/ ./
RUN npm run build
EXPOSE 8080
CMD ["npm", "start"]
