FROM ubuntu:18.04

ENV HUGO_VERSION=0.122.0

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    curl git ca-certificates tar bash \
 && rm -rf /var/lib/apt/lists/*

# Descargar y extraer Hugo
RUN curl -L https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_Linux-64bit.tar.gz \
    -o /tmp/hugo.tar.gz \
 && tar -xzf /tmp/hugo.tar.gz -C /tmp \
 && mv /tmp/hugo /usr/local/bin/hugo \
 && chmod +x /usr/local/bin/hugo \
 && rm /tmp/hugo.tar.gz

WORKDIR /src

CMD ["hugo", "server", "--bind", "0.0.0.0", "-D"]
