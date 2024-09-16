FROM ruby:3.3.0-slim

# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

WORKDIR /opt/microservices

COPY Gemfile Gemfile.lock details.rb ./
RUN bundle install
RUN useradd -u 1000 -m myuser

COPY . .

EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]
