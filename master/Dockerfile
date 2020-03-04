FROM elixir:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get update && \
    apt-get install -y -q nodejs && \
    apt-get install -y inotify-tools && \
    apt-get autoclean

RUN mix local.hex --force
RUN mix local.rebar --force
RUN mix archive.install hex phx_new --force

WORKDIR /app
EXPOSE 4000
