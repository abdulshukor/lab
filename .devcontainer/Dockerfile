FROM mcr.microsoft.com/devcontainers/base:ubuntu24.04

RUN apt-get update \
    && apt-get install -y --no-install-recommends iptables nftables \
    && update-alternatives --set iptables /usr/sbin/iptables-nft \
    && update-alternatives --set ip6tables /usr/sbin/ip6tables-nft \
    && rm -rf /var/lib/apt/lists/*

COPY --from=jdxcode/mise /usr/local/bin/mise /usr/local/bin/

RUN echo 'eval "$(mise activate bash)"' >> /home/vscode/.bashrc \
    && echo 'eval "$(mise activate zsh)"' >> /home/vscode/.zshrc
