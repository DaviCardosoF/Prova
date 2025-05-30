FROM php:8.2-cli

# Instalar extensões necessárias
RUN apt-get update && apt-get install -y \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && docker-php-ext-install pdo pdo_mysql

# Copiar os arquivos da API
COPY . /var/www/html
WORKDIR /var/www/html

# Permissões
RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html

EXPOSE 3003
CMD ["php", "-S", "0.0.0.0:3003", "-t", "/app"]