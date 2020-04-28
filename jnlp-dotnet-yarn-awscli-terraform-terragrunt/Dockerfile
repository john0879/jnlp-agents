FROM john0879/jnlp-dotnet-yarn-awscli-terraform

USER root

# Install Terragrunt
ENV VERSION 0.23.12
ENV URL "https://github.com/gruntwork-io/terragrunt/releases/download/v${VERSION}/terragrunt_linux_amd64"
ENV CHECKSUM "1d6b0d01627a5465170e746b3d8a54c13295189df1ef8bb4cee5e5264c9fa6e3"

RUN curl -sL "${URL}" -o /bin/terragrunt \
	&& echo "${CHECKSUM} /bin/terragrunt" | sha256sum -c - \
	&& chmod +x /bin/terragrunt

USER jenkins