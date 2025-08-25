FROM redmine:latest

# Cambiar a usuario root para instalar dependencias
USER root

# Instalar git si no está disponible
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

# Cambiar al directorio de Redmine
WORKDIR /usr/src/redmine

# Instalar plugin Additionals 
RUN git clone -b stable https://github.com/alphanodes/additionals.git plugins/additionals

# Configurar bundler y instalar dependencias
RUN bundle config set --local without 'development test' && \
    bundle install

USER redmine