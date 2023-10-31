FROM node:20-alpine3.17

RUN apk update
RUN apk add --no-cache git

WORKDIR /src/

RUN git clone https://github.com/HiroyukiNaito/uniswap-universal-graphql.git

# For local development
# COPY ./src .

RUN cd /src/uniswap-universal-graphql/ && yarn install

WORKDIR /src/

COPY ./runGraphQL.sh .

RUN chmod +x runGraphQL.sh
