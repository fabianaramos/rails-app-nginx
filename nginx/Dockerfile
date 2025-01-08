FROM nginx:alpine

# Atualiza os pacotes e instala utilitários necessários
RUN apk add --no-cache apache2-utils bash

# Define o diretório raiz da aplicação
ENV RAILS_ROOT /var/www/rails_app
WORKDIR $RAILS_ROOT

# Cria as pastas necessárias
RUN mkdir -p log tmp/pids tmp/sockets public/assets public/packs

# Copia a configuração customizada do Nginx
COPY nginx/app.conf /etc/nginx/conf.d/default.conf

# Ajusta permissões (se necessário)
RUN chown -R nginx:nginx $RAILS_ROOT

# Expõe a porta 80
EXPOSE 80

# Comando para iniciar o Nginx
CMD ["nginx", "-g", "daemon off;"]
