FROM node:9-alpine
MAINTAINER Yoshiyuki Ieyama <yukku0423@gmail.com>
WORKDIR /opt
RUN apk --update --no-cache add git python make g++ zeromq-dev musl-dev \
  && git clone https://github.com/nemtech/catapult-rest.git -b master --depth=1 \
  && cd catapult-rest && ./yarn_setup.sh \
  && cd rest && npm run build
WORKDIR /opt/catapult-rest/rest
CMD ["npm", "start", "resources/rest.json"]
