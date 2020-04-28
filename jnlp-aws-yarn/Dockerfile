FROM john0879/jnlp-aws

USER root

# set up node and yarn
ENV NODE_VERSION 10.19.0
ENV YARN_VERSION 1.17.3
ENV NODE_DOWNLOAD_SHA 36d90bc58f0418f31dceda5b18eb260019fcc91e59b0820ffa66700772a8804b
ENV NODE_DOWNLOAD_URL https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz

RUN curl -SL "$NODE_DOWNLOAD_URL" --output nodejs.tar.gz \
	&& echo "$NODE_DOWNLOAD_SHA nodejs.tar.gz" | sha256sum -c - \
	&& tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 \
	&& rm nodejs.tar.gz \
	&& npm i -g yarn@$YARN_VERSION \
	&& ln -s /usr/local/bin/node /usr/local/bin/nodejs

USER jenkins