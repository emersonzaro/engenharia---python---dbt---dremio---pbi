# Dremio Data Virtualization

Esse projeto consiste em simular um ambiente de BigData local onde vamos realizar um processo de ELT. 

## O que é o Dremio

O Dremio é uma plataforma aberta de data lakehouse que permite consultar e analisar dados diretamente de fontes variadas (como data lakes, bancos SQL e NoSQL) sem precisar mover, copiar ou duplicar as informações

## Principais características

- Virtualização de Dados: Permite criar visões virtuais unificadas sobre múltiplas fontes de armazenamento.
- Tecnologia Apache Arrow: Usa processamento colunar em memória para garantir alto desempenho e consultas SQL de baixa latência.
- Integração com BI: Conecta-se de forma nativa a ferramentas de visualização como Power BI e Tableau.
- Data Reflections: Funcionalidade que acelera as consultas por meio de materialização física inteligente dos dados.
- Arquitetura Aberta: Baseado em padrões como Apache Iceberg, Apache Parquet e Apache Calcite

## Arquitetura
![image](assets/architecture.png)

- A ingestão será feita com Python para o Minio
- O Dremio está virtualizando todos os arquivos do Minio
- O dbt será responsável por processar as camadas inter e mart
- O Power BI vai conectar no Dremio e fazer exibição dos dados.

## Pré-requisitos
* Docker
* Python 
* Power BI Desktop

## Como utilizar o projeto?
clone o repositório com o comando:
```
git clone https://github.com/emersonzaro/engenharia---python---dbt---dremio---pbi
```
Entre na pasta do projeto:
```
cd engineering-python-dbt-dremio-pbi
```
Crie o ambiente virtual
```
python3 -m venv venv
```
Ative o ambiente virtual
Linux
```
source venv/bin/activate
```
Windows
```
venv/scripts/activate
```
Instale as libs do Python
```
pip install -r requirements.txt
```

## Como subir o serviço do Dremio com o Minio?
Entre na pasta ```docker``` e execute o comando:
```
sudo docker compose up -d
```

## Como rodar a ingestão com Python?
Entre na pasta ```src/pyingestor``` e execute o programa ```main.py```
```
python3 main.py
```

## Como rodar o processamento com dbt?
Entre na pasta ```src/dbt_dremio``` e execute o comando 

```
dbt run
```

## Como acessar os serviços?

### Minio
```
minio: localhost:9000
login: admin 
senha: password
```

### Dremio
```
dremio: localhost:9047
login: dremio
senha: dremio123
```

## Como conectar o Power BI ao Dremio?
Busque pelo conector do Dremio 

![image](assets/dremio-connector.png)

E use os parâmetros para conectar:
```
localhost:31010
encrypt: disabled
```

## 📚 Referências

https://github.com/dremio/dbt-dremio


## Developer
| Desenvolvedor      | LinkedIn                                   | Email                        | Portfólio                              |
|--------------------|--------------------------------------------|------------------------------|----------------------------------------|
| Emerson Zaro   | [LinkedIn](https://www.linkedin.com/in/ezaro/) | emersonzaro@gmail.com        | [Portfólio](https://github.com/emersonzaro/)   |
