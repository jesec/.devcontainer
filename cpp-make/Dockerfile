FROM ubuntu:focal

COPY ./.devcontainer/library-scripts /tmp/library-scripts/

# Configure base container
RUN /bin/bash /tmp/library-scripts/common-debian.sh true vscode 1000 1000 true

# Install development tools
RUN apt update
RUN apt install -y \
    bear build-essential clang-format git gdb zsh

# Run as vscode user
USER vscode

# Apply shell customizations
RUN git clone https://github.com/jesec/.dotfiles.git ~/.dotfiles
RUN cd ~/.dotfiles && bash setup.sh
