# docker build --rm -t nvidia-centos7 .

FROM indigodatacloud/centos-sshd:7
MAINTAINER Mario David <mariojmdavid@gmail.com>
LABEL description="NVIDIA GPU" \
      org.label-schema.vcs-url="https://github.com/LIP-Computing/ansible-role-nvidia"

RUN ansible-galaxy install LIP-Computing.ansible-role-nvidia,nvdrv_352.93 && \
    ansible-playbook /etc/ansible/roles/LIP-Computing.ansible-role-nvidia/tests/install-docker.yml
