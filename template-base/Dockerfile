# This Dockerfile uses a distroless Node.js 24 image based on Debian 12 as the base image.
# For the Backstage Lab, you should not need to modify this file.

FROM gcr.io/distroless/nodejs24-debian12

WORKDIR /app
COPY src/main.js ./
EXPOSE 8000

# These will be replaced during template rendering
ARG SERVICE_NAME="${{ values.name }}"
ARG SERVICE_DESCRIPTION="${{ values.description }}"
ARG SERVICE_OWNER="${{ values.owner }}"

# Set metadata using the build args
LABEL service.name="${SERVICE_NAME}"
LABEL service.description="${SERVICE_DESCRIPTION}"
LABEL service.owner="${SERVICE_OWNER}"

CMD ["main.js"]