# Lab: Wordpress Dockered

Projeto Wordpress rodando em um container Docker com Banco de Dados (MariaDB) persistente

---

## Inicializando e/ou Parando o ambiente do projeto

Para rodar a imagem localmente, digite:

``# docker-compose up -d``

Para PARAR a imagem localmente, digite:

``# docker-compose down``

Se quiser, além de remover a imagem/container e os dados do banco de dados, digite:

``# docker-compose down --volumes --remove-orphans``

---

### Em produção

Será necessário rodar o comando do ``docker-compose`` um pouco diferente, agora, referenciando o arquivo com variáveis inerentes ao ambiente de PROD, a seguir:

``# docker-compose -f docker-compose.yml -f docker-compose.prod.yml up``


---

## Trabalhando com o projeto

Os arquivos de trabalho devem ser armazenados em:

 - Temas: ``wp-content/themes/``
 - Plugins: ``wp-content/plugins``
 - Uploads: ``wp-content/uploads``

Eles podem ser trabalhados normalmente e localmente, e ao serem atualizados já refletem as alterações feitas.

### No browser, você deve acessar com ``http://localhost:8080`` 

---

## Links de referência

 - https://docs.docker.com/compose/wordpress/#shutdownclean-up
 - https://www.youtube.com/watch?v=XyFJx9APCHk
 - https://www.youtube.com/watch?v=pkp_Dr_4pOA
 - https://github.com/docker/compose/issues/3874
