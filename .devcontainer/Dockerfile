FROM mcr.microsoft.com/devcontainers/universal:2-linux

# Install necessary dependencies
RUN apt-get update && \
    apt-get install -y gnupg wget xz-utils

# Add MongoDB's official GPG key and repository
RUN wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add - && \
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs)/mongodb-org/6.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-6.0.list

# Install MongoDB
RUN apt-get update && apt-get install -y mongodb-org && \
    pip install django pymongo

# Start MongoDB when the container runs
CMD ["mongod", "--bind_ip", "0.0.0.0"]