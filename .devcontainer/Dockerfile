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

RUN touch /home/vscode/.zshrc.local && chown vscode:vscode /home/vscode/.zshrc.local

# make sure mise is activated in zsh. Might be overridden by a user's dotfiles.
RUN echo 'eval "$(mise activate zsh)"' >> /home/vscode/.zshrc.local

# enable mise completion
RUN echo 'source <(mise completion zsh)' >> /home/vscode/.zshrc.local

# enable flux completion
RUN echo 'source <(flux completion zsh)' >> /home/vscode/.zshrc.local

# enable k3d completion
RUN echo 'source <(k3d completion zsh)' >> /home/vscode/.zshrc.local

