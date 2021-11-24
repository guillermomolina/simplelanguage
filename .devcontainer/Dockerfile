FROM ghcr.io/graalvm/graalvm-ce:java11-21.3

LABEL org.opencontainers.image.authors "Guillermo Adrián Molina <guillermoadrianmolina@hotmail.com>"

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000
#ARG USER_GID=$USER_UID

RUN microdnf install -y git maven unzip shadow-utils sudo
#RUN gu install native-image

# Create the user
RUN groupadd --gid $USER_GID $USERNAME && \
    useradd --uid $USER_UID --gid $USER_GID -m $USERNAME && \
    echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME && \
    chmod 0440 /etc/sudoers.d/$USERNAME

# RUN gu install -L /sl/component/sl-component.jar

# WORKDIR /workspaces

# ENTRYPOINT ["/opt/graalvm-ce-java11-21.3.0/bin/sl"]

# [Optional] Set the default user. Omit if you want to keep the default as root.
USER $USERNAME
