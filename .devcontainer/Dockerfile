FROM mcr.microsoft.com/devcontainers/universal:2-linux

# Install necessary packages including MongoDB
RUN apt-get update && apt-get install -y xz-utils gnupg wget && \
    wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add - && \
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs)/mongodb-org/6.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-6.0.list && \
    apt-get update && \
    apt-get install -y mongodb-org

# Install Django and pymongo
RUN pip install django pymongo