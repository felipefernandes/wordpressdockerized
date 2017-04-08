# Wordpress Dockerizado

Projeto Wordpress rodando em um container Docker com Banco de Dados (MariaDB) persistente.

---

### Estrutura do projeto

* `/db-data` 				 é onde serão guardado os dados do mysql
* `/wp-content` 			diretório padrão de conteúdo do Wordpress
* `/wp-content/plugins` 	diretório onde você vai guardar os seus plugins
* `/wp-content/themes` 		diretório onde você vai guardar os seus temas
* `/wp-content/uploads`		diretório onde serão guardadas as mídias

## Primeiros passos

Antes de começar, você precisar do Docker instalado na sua máquina. Você pode baixar [aqui](https://docs.docker.com/engine/installation/).

Depois, você vai precisar editar o arquivo `docker-compose.yml` o atualizando com o caminho (completo) do projeto na sua máquina. So duas linhas que fazem referência aos Volumes (espécie de mapeamento/link da sua máquina com o container), assim:

```
    volumes:
       - <TROQUE PELA PASTA ONDE FICARA SEU PROJETO>/wp-content:/var/lib/mysql
```
Feito isso, é só passar para o passo de **Inicializar o ambiente**.

---

## Inicializando e/ou Parando o ambiente do projeto

Para rodar a imagem localmente, digite:

``# docker-compose up -d``

Para PARAR a imagem localmente, digite:

``# docker-compose down``

Se quiser, além de remover a imagem/container e os dados do banco de dados, digite:

``# docker-compose down --volumes --remove-orphans``


### No browser, para acessar, você deve acessar com ``http://localhost:8080`` 

---

## Trabalhando com o projeto

Os arquivos de trabalho devem ser armazenados em:

 - Temas: ``wp-content/themes/``
 - Plugins: ``wp-content/plugins``
 - Uploads: ``wp-content/uploads``

Eles podem ser trabalhados normalmente e localmente, e ao serem atualizados já refletem as alterações feitas.


---

### Em produção (BETA)

Se você quiser colocar em um servidor e usar o docker, será necessário rodar o comando do ``docker-compose`` um pouco diferente, agora, referenciando o arquivo com variáveis inerentes ao ambiente de PROD (portas do mysql, http, e etc.). Após clonar o repo no servidor (com seus respectivos arquivos), rode o comando a seguir no bash do servidor:

``# docker-compose -f docker-compose.yml -f docker-compose.prod.yml up``

---

## Links de referência

 - https://docs.docker.com/compose/wordpress/#shutdownclean-up
 - https://www.youtube.com/watch?v=XyFJx9APCHk
 - https://www.youtube.com/watch?v=pkp_Dr_4pOA
 - https://github.com/docker/compose/issues/3874

