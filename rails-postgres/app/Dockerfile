FROM ruby:3.1

RUN mkdir /app && useradd -m app && chown app /app

RUN apt-get update -qq && apt-get install -y --no-install-recommends postgresql-client

USER app

WORKDIR /app

COPY --chown=app:app Gemfile* .
RUN bundle install

COPY --chown=app:app . .

EXPOSE 3000

CMD ["bundle", "exec", "rails", "server", "-b", "0.0.0.0"]
