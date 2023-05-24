FROM ghcr.io/daringway/docker-dev-env-utils:1.0.0 as builder

RUN install-node        18.16.0 

# Needed for expo https://facebook.github.io/watchman/docs/install
# this install v4.9.0 which is 6 years old, but build from source fails
RUN sudo apt-get install -y watchman

RUN cleanup-install

FROM builder as devcontainer
RUN echo "Docker Desktop Dev Environment" >> ~/hello

FROM builder as default
RUN echo "default builder" >> ~/hello
CMD bash