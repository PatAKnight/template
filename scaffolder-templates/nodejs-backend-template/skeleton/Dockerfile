# Stage 1 - Install dependencies
FROM registry.access.redhat.com/ubi9/nodejs-18-minimal:latest AS deps

COPY package.json package-lock.json ./
RUN npm ci

# Stage 3 - Production image, copy all the files and start NodeJS
FROM registry.access.redhat.com/ubi9/nodejs-18-minimal:latest AS runner

ENV NODE_ENV production

# Switch to nodejs user
USER 1001

COPY . .
COPY --from=deps /opt/app-root/src .

ENV PORT ${{ values.port }}
EXPOSE ${{ values.port }}

CMD ["node", "src/index.ts"]
