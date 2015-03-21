FROM guojian/nodejs

RUN cd /tmp && \
  wget  --no-check-certificate https://ghost.org/zip/ghost-latest.zip

# Install Ghost
RUN apt-get install -y unzip git

RUN \
  cd /tmp && \
  unzip ghost-latest.zip -d /ghost && \
  rm -f ghost-latest.zip

RUN \
  cd /ghost && \
  npm install --production

RUN \
  sed 's/127.0.0.1/0.0.0.0/' /ghost/config.example.js > /ghost/config.js && \
  useradd ghost --home /ghost

# Add files.
ADD start.bash /ghost-start

# Set environment variables.
ENV NODE_ENV production

# Define mountable directories.
VOLUME ["/data", "/ghost-override"]

# Define working directory.
WORKDIR /ghost

# Define default command.
CMD ["bash", "/ghost-start"]

# Expose ports.
EXPOSE 2368
