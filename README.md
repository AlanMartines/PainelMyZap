# 🚀 Painel MyZap2.0 Com ZendFramework

## Descrição

Esse é um painel criado como estudo pessoal do framework (Zend Framework MVC) 
não foi criado para fins comerciais, mas você está livre para utilizar, e melhorar
da forma que quiser.
## 📖 Instalação
Clone o repositorio oficial

```bash
$ git clone https://github.com/jhowbhz/PainelMyZap.git /opt/PainelMyZap
```
## 🕒 Crontab checagem sessões
```bash
# adicionar permissao
$ chmod -R 0777 /opt/PainelMyZap/cron/cron.sh

# abrir o crontab
$ crontab -e

# Adicione a linha
$ 0 5 * * * /opt/PainelMyZap/cron/cron.sh --quiet
```
## ⚙️ Configurando 

```bash
# Altere a linha ```CHAVE_WEBOOK=1234```
$ nano /opt/PainelMyZap/config/application.config.php
```
## 🌎 Iniciando servidor web

```bash
$ cd /opt/PainelMyZap
$ php -S 0.0.0.0:8080 -t public
# ou use o composer
$ composer run --timeout 0 serve
```
## 📌 Utilizando com Nginx
```nginx
server {
    listen       80;
    server_name  zfapp.localhost;
    root         /path/to/zfapp/public;

    location / {
        index index.php;
        try_files $uri $uri/ @php;
    }

    location @php {
        # Pass the PHP requests to FastCGI server (php-fpm) on 127.0.0.1:9000
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_param  SCRIPT_FILENAME /path/to/zfapp/public/index.php;
        include fastcgi_params;
    }
}
```
## 🏃Pronto, agora é so iniciar o painel

```bash
$ cd path/to/install
$ php -S 0.0.0.0:8080 -t public
# OR use the composer alias:
$ composer run --timeout 0 serve
```
