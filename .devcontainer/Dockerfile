DE debian:bullseye-slim
ARG DEBIAN_FRONTEND=não interativo
USUÁRIO root
COPIAR php.ini /tmp

EXECUTE apt-get update -yq
    # Adicionar fontes php atualizadas
EXECUTE apt-get install curl -yq
EXECUTE curl -sSL https://packages.sury.org/php/README.txt | bash -x
EXECUTE apt-get update -yq
    # Instale alguns pacotes comuns
EXECUTE apt-get install git imagemagick nano openssh-server sqlite3 wget unzip -yq
EXECUTE sed -i 's/<política domínio="codificador" direitos="nenhum" padrão="PDF" \/>/<política domínio="codificador" direitos="leitura|escrita" padrão="PDF" \/>/g' /etc/ImageMagick-6/policy.xml
    # Instale o PHP CLI com algumas extensões para desenvolvimento Drupal
EXECUTE apt-get install php8.2-dev -yq
EXECUTE apt-get install php8.2-apcu php8.2-curl php8.2-gd php8.2-imagick php8.2-mbstring php8.2-sqlite3 php8.2-zip php8.2-intl -yq
EXECUTE pear config-set php_ini /etc/php/8.2/cli/php.ini
EXECUTE pecl install xdebug
EXECUTE cat /tmp/php.ini >> /etc/php/8.2/cli/php.ini
    # Instalar NodeJS LTS
EXECUTE curl -sL https://deb.nodesource.com/setup_lts.x | bash
EXECUTE apt-get install nodejs -yq
    # Instalar o Composer
EXECUTE wget https://getcomposer.org/installer
EXECUTE o instalador do php --install-dir=/usr/local/bin --filename=composer