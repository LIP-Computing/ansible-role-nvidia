# docker build --rm -t os-cli-centos7 .

FROM lipcomputing/ansible-centos7
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="NVIDIA GPU" \
      org.label-schema.vcs-url="https://github.com/LIP-Computing/ansible-role-nvidia"

RUN ansible-galaxy install LIP-Computing.ansible-role-nvidia && \
    ansible-playbook /etc/ansible/roles/LIP-Computing.ansible-role-nvidia/tests/install-docker.yml
