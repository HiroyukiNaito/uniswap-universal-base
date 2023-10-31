FROM node:18-alpine3.17

RUN apk update
RUN apk add --no-cache git

WORKDIR /src/

RUN git clone https://github.com/HiroyukiNaito/uniswap-universal-decoder.git
RUN git clone https://github.com/HiroyukiNaito/uniswap-universal-batcher.git
RUN git clone https://github.com/HiroyukiNaito/uniswap-universal-publisher.git

# For development
# COPY ./src/ .

RUN cd /src/uniswap-universal-decoder/ && yarn install 
RUN cd /src/uniswap-universal-batcher/ && yarn install 
RUN cd /src/uniswap-universal-publisher/ && yarn install 

WORKDIR /src/

COPY ./runBatch.sh .
COPY ./runPublish.sh .

RUN chmod +x runBatch.sh 
RUN chmod +x runPublish.sh
