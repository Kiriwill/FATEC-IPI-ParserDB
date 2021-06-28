DelafParserDB 
----
DelafParserDB é um banco de palavras em Português-brasileiro para processamento sintático construido com base no dicionário do [Projeto Unitex-PB](http://www.nilc.icmc.usp.br/nilc/projects/unitex-pb/web/index.html). É um resultado do Programa de Iniciacão científica e Tecnológica da FATEC - Ipiranga.

## Autores
PACHECO, Willian. 
[Banco de dados para análise sintática em sentenças do português brasileiro.](https://github.com/Kiriwill/FATEC-IPI-ParserDB/blob/master/Projeto%20de%20Pesquisa%20do%20Programa%20de%20Iniciacao%20Cientifica%20ou%20Tecnologica%20-%20Willian.pdf)

Orientador: Manoel Francisco Guaranha


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

