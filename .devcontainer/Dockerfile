FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

ARG VERUS_VERSION=0.2025.05.26.cb05dfc

USER vscode
SHELL ["/bin/bash", "-c"]

WORKDIR /verus
RUN wget https://github.com/verus-lang/verus/archive/refs/tags/release/${VERUS_VERSION}.zip \
    && unzip ${VERUS_VERSION}.zip \
    && rm ${VERUS_VERSION}.zip \
    && find verus-release-${VERUS_VERSION} -mindepth 1 -maxdepth 1 -exec mv -t ./ {} + \
    && curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y \
    && . "$HOME/.cargo/env" \
    && cd source \
    && ./tools/get-z3.sh \
    && source ../tools/activate \
    && vargo build --release \
    && chown -R vscode:vscode /verus

ENV PATH="/verus/source/target-verus/release:${PATH}"
ENV PATH="/verus/tools/vargo/target/release:${PATH}"
