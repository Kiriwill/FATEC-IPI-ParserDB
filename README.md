DelafParserDB 
----
Um banco de palavras em Português-brasileiro para processamento sintático construido com base no dicionário do [Projeto Unitex-PB](http://www.nilc.icmc.usp.br/nilc/projects/unitex-pb/web/index.html).

## Autores
PACHECO, Willian. 
Banco de dados para análise sintática em sentenças do português brasileiro.


## Instalação

Na pasta raiz crie e execute o container com o PostgreSQL 12.7:
```bash
docker-compose up -d --force-recreate
```

Em seguida é só restaurar os dados do arquivo *`parserDB.backup`*:

```bash
docker exec -i UnitexParserDB bin/bash -c "psql -U parserUser -d parserDB" < parserDB.backup 
```

### Requisitos de sistema

Banco: PostgreSQL > 12.6 <br/>
Docker 20.10.5

> obs: o arquivo *docker-compose.yml* mapeia a porta *5432* do container para a porta *5433* da máquina local. Ambas devem estar disponíveis portanto.

