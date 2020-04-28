FROM jenkins/jnlp-slave

USER root

RUN apt-get update && apt-get install unzip

# Install AWS CLI
ENV AWSCLI_ZIP "awscliv2.zip"

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o ${AWSCLI_ZIP} \
	&& unzip ${AWSCLI_ZIP} \
	&& ./aws/install \
	&& rm ${AWSCLI_ZIP}

# Install Terraform
ENV VERSION 0.12.24
ENV URL "https://releases.hashicorp.com/terraform/${VERSION}/terraform_${VERSION}_linux_amd64.zip"
ENV CHECKSUM "602d2529aafdaa0f605c06adb7c72cfb585d8aa19b3f4d8d189b42589e27bf11"

RUN curl -SL "${URL}" --output terraform.zip \
	&& echo "${CHECKSUM} terraform.zip" | sha256sum -c - \
	&& unzip "terraform.zip" -d /usr/local/bin \
	&& rm terraform.zip

# Install Terragrunt
ENV VERSION 0.23.12
ENV URL "https://github.com/gruntwork-io/terragrunt/releases/download/v${VERSION}/terragrunt_linux_amd64"
ENV CHECKSUM "1d6b0d01627a5465170e746b3d8a54c13295189df1ef8bb4cee5e5264c9fa6e3"

RUN curl -sL "${URL}" -o /bin/terragrunt \
	&& echo "${CHECKSUM} /bin/terragrunt" | sha256sum -c - \
	&& chmod +x /bin/terragrunt

USER jenkins