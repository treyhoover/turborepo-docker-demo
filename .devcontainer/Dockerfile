FROM node:22-alpine

# Install necessary packages
RUN apk add --no-cache git

# Install pnpm
RUN npm install -g pnpm

# Set working directory
WORKDIR /workspace

# Set pnpm store directory
ENV PNPM_HOME="/root/.local/share/pnpm"
ENV PATH="${PATH}:${PNPM_HOME}"

# Ensure pnpm store directory exists
RUN mkdir -p /root/.local/share/pnpm && chown -R node:node /root/.local/share/pnpm

# Ensure /workspace and /workspace/node_modules directories are owned by node user
RUN mkdir -p /workspace/node_modules && chown -R node:node /workspace

# Use non-root user for better security
USER node

# Install dependencies
RUN pnpm install

# Expose the port the app runs on (if applicable)
EXPOSE 3000