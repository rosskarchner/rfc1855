FROM amazonlinux:2

RUN yum update -y && amazon-linux-extras enable docker python3.8  && yum clean metadata && yum install -y git docker python38-pip unzip make\
    && rm -rf /var/cache/yum && pip3.8 install -U pip setuptools
RUN mkdir /tmp/awscli-install  \
  && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "/tmp/awscli-install/awscliv2.zip" \
  && unzip /tmp/awscli-install/awscliv2.zip -d /tmp/awscli-install \
  && /tmp/awscli-install/aws/install && rm -rf /tmp/awscli-install

RUN mkdir /tmp/samcli-install  \
  && curl -L "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip" -o "/tmp/samcli-install/aws-sam-cli-linux-x86_64.zip" \
  && unzip /tmp/samcli-install/aws-sam-cli-linux-x86_64.zip -d /tmp/samcli-install \
  && /tmp/samcli-install/install && rm -rf /tmp/samcli-install
