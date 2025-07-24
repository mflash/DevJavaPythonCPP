# Imagem base com Java 21 (OpenJDK) e Maven pré-instalados
FROM mcr.microsoft.com/devcontainers/java:1-21-bookworm

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# Atualização de pacotes e instalação do Graphviz, Python e GCC/G++ em um único layer
# Python precisa ser instalado pós-inicialização com uv python install (pelo terminal)
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y graphviz g++ && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

