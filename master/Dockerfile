FROM elixir:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | tee /etc/apt/sources.list.d/google-chrome.list
RUN apt-get update && \
    apt-get install -y -q nodejs && \
    apt-get install -y inotify-tools && \
    apt-get install -y libnss3 && \
    apt-get install -y google-chrome-stable && \
    apt-get install -y postgresql-client && \
    apt-get autoclean

RUN mix local.hex --force
RUN mix local.rebar --force
RUN mix archive.install hex phx_new --force

WORKDIR /app
EXPOSE 4000
