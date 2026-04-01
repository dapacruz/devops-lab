FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
ENV MISE_DATA_DIR="/mise"
ENV MISE_CONFIG_DIR="/mise"
ENV MISE_CACHE_DIR="/mise/cache"
ENV MISE_INSTALL_PATH="/usr/local/bin/mise"
ENV PATH="/mise/shims:$PATH"
# ENV MISE_VERSION="..."
RUN mkdir -p /mise && chown -R vscode:vscode /mise

RUN curl https://mise.run | sh

# make sure mise is activated in both zsh and bash. Might be overridden by a user's dotfiles.
RUN echo 'eval "$(mise activate zsh)"' >> /home/vscode/.zshrc.local

