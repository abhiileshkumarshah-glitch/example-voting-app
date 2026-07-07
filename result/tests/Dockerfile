FROM node:20-slim

# Use a maintained Node LTS base image for security and package support
RUN apt-get update -qq && apt-get install -qy \
    ca-certificates \
    bzip2 \
    curl \
    libfontconfig \
    --no-install-recommends && rm -rf /var/lib/apt/lists/*

# phantomjs-prebuilt is deprecated but kept for test compatibility
RUN yarn global add phantomjs-prebuilt
ADD . /app
WORKDIR /app
CMD ["/app/tests.sh"]
