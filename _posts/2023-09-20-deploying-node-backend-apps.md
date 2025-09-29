---
title: Deploy de uma Aplicação Backend Node.js
author: gsdesenvolvedor
date: 2025-09-29 13:31:00 +0300
categories: [Deploy, Node.js, AWS]
tags: [Deploy, Node.js, AWS]
pin: true
---

## Pré-requisitos

- Servidor com Ubuntu/Linux
- Acesso SSH ao servidor
- Node.js e npm instalados
- Git instalado
- Nginx instalado (opcional para proxy reverso)
- PM2 instalado (para gerenciamento do processo)

---

## 1. Acesse o servidor via SSH

```sh
ssh usuario@ip_do_servidor
```

---

## 2. Instale Node.js e npm (caso não tenha)

```sh
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

---

## 3. Instale o Git (caso não tenha)

```sh
sudo apt-get update
sudo apt-get install git
```

---

## 4. Clone seu repositório

```sh
git clone https://github.com/usuario/repositorio.git
cd repositorio
```

---

## 5. Instale as dependências

```sh
npm install
```

---

## 6. Crie o arquivo de variáveis de ambiente (.env) se necessário

```sh
nano .env
```
(Prencha com suas configurações)

---

## 7. Instale o **PM2** para gerenciar o processo

```sh
sudo npm install -g pm2
```

---

## 8. Inicie a aplicação com PM2

```sh
pm2 start src/app.js --name nome-da-sua-app
```
> Altere o caminho conforme sua estrutura de projeto.

---

## 9. (Opcional) Configure o PM2 para iniciar na reinicialização do servidor

```sh
pm2 startup
pm2 save
```

---

## 10. (Opcional) Configure o Nginx como proxy reverso

1. Edite o arquivo de configuração do Nginx:

    ```sh
    sudo nano /etc/nginx/sites-available/default
    ```

2. Adicione o seguinte bloco ao servidor:

    ```
    server {
        listen 80;
        server_name seu_dominio.com;

        location / {
            proxy_pass http://localhost:3000;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
    }
    ```

    > Altere `seu_dominio.com` e a porta (`3000`) conforme seu caso.

3. Teste o Nginx e recarregue:

    ```sh
    sudo nginx -t
    sudo systemctl reload nginx
    ```

---

## 11. Verifique se está rodando

- Acesse `http://ip_do_servidor` ou `http://seu_dominio.com` no navegador.

---

# Referências

- [Documentação do PM2](https://pm2.keymetrics.io/docs/usage/quick-start/)
- [Documentação do Nginx](https://nginx.org/en/docs/)

