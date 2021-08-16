FROM amazonlinux:latest

RUN yum update -y && amazon-linux-extras enable docker python3.8  && yum clean metadata && yum install -y sudo tar git docker python38-pip unzip make\
    && rm -rf /var/cache/yum
RUN mkdir /tmp/awscli-install  \
  && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "/tmp/awscli-install/awscliv2.zip" \
  && unzip /tmp/awscli-install/awscliv2.zip -d /tmp/awscli-install \
  && /tmp/awscli-install/aws/install && rm -rf /tmp/awscli-install

RUN mkdir /tmp/samcli-install  \
  && curl -L "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip" -o "/tmp/samcli-install/aws-sam-cli-linux-x86_64.zip" \
  && unzip /tmp/samcli-install/aws-sam-cli-linux-x86_64.zip -d /tmp/samcli-install \
  && /tmp/samcli-install/install && rm -rf /tmp/samcli-install

# Create the user
RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode \
    && chown -R $USER_UID:$USER_GID /home/$USERNAME \
    && echo vscode ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/vscode \
    && chmod 0440 /etc/sudoers.d/vscode

USER vscode
RUN pip3.8 install -U --user pip setuptools black cfn-lint