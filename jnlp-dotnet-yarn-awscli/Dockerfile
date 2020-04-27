FROM john0879/jnlp-dotnet-yarn

USER root

ENV AWSCLI_ZIP "awscliv2.zip"

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o ${AWSCLI_ZIP} \
	&& unzip ${AWSCLI_ZIP} \
	&& ./aws/install \
	&& rm ${AWSCLI_ZIP}

USER jenkins