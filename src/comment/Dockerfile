FROM alpine:latest


WORKDIR /app

COPY . /app

ENV COMMENT_DATABASE_HOST comment_db
ENV CMMENT_DATABASE comments


RUN apk update \
	&& apk add --no-cache build-base \
	                      ruby \
	                      ruby-bundler \
	                      ruby-dev \
	                      ruby-json \
	&& gem install bundler --no-ri --no-rdoc \
	&& bundle install && apk del build-base ruby-dev \
	&& rm -rf /usr/share/terminfo/ \
	&& rm -rf /root/.bundle/cache/

CMD ["puma"]