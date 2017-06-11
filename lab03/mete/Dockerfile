FROM aarch64/alpine

RUN apk --update add ruby-dev build-base ruby-bigdecimal ruby-irb ruby-bundler git linux-headers sqlite-dev zlib-dev nodejs

COPY ./ mete/
WORKDIR /mete

EXPOSE 8080
VOLUME /mete/database
VOLUME /mete/public/system
VOLUME /mete/public/assets

ENV RAILS_ENV=production
RUN bundle install --path vendor/bundle
RUN bundle exec rake assets:precompile
CMD bundle exec unicorn
