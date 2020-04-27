FROM john0879/jnlp-dotnet-yarn-awscli

USER root

RUN apt-get update && apt-get install unzip

ENV VERSION 0.12.24
ENV URL "https://releases.hashicorp.com/terraform/${VERSION}/terraform_${VERSION}_linux_amd64.zip"
ENV CHECKSUM "602d2529aafdaa0f605c06adb7c72cfb585d8aa19b3f4d8d189b42589e27bf11"

RUN echo $URL

RUN curl -SL "$URL" --output terraform.zip \
	&& echo "$CHECKSUM terraform.zip" | sha256sum -c - \
	&& unzip "terraform.zip" -d /usr/local/bin \
	&& rm terraform.zip

USER jenkins