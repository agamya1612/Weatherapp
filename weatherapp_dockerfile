# Use Ubuntu as the base image
FROM ubuntu:latest

# Set the working directory to /app
WORKDIR /app

# Install dependencies (Git, Node.js, Gulp, etc.)
RUN apt-get update -y && \
    apt-get install -y \
    curl \
    git \
    gnupg2 \
    lsb-release \
    ca-certificates \
    python3 \
    python3-pip \
    build-essential

# Install Node.js (LTS version)
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

# Install Gulp globally
RUN npm install -g gulp-cli

# Clone the repository from GitHub
RUN git clone https://github.com/Yashchaudhary05/weather_app.git .

# Install project dependencies
RUN npm install

# Expose port 3000 for the app
EXPOSE 3000

# Run the app using Gulp
CMD ["gulp", "sync"]
