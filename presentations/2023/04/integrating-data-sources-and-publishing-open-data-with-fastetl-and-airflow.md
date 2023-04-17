---
marp: true
theme: default
style: |
  @import 'https://fonts.googleapis.com/css?family=Fira+Sans:300,500';
  section {
    font-family: 'Fira Sans', sans-serif;
  }
  section.lead > p > em {
    color: white;
    background-color: #730302;
    padding: 5px 20px 10px;
    font-style: normal;
  }
  section:not(.lead) {
    background-image: url('/slide-decks/images/alex-lvrs-Md6_qA-BMis-unsplash.jpg');
  }
  section:not(.lead)::before {
    content: 'csv,conf,v7';
    position: absolute;
    bottom: 5px;
    left: 20px;
    color: white;
    height: 40px;
    text-align: left;
    border-bottom: 5px solid #f9afa8;
    padding: 5px 0 5px 0px;
    z-index: 2;
  }
  section:not(.lead)::after {
    color: white;
    background-color: #730302;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 60px;
    padding: 5px 20px 0 0;
    text-align: right;
    z-index: 1;
  }
  .container {
    display: flex;
  }
  .col {
    flex: 1;
  }
---

<!-- _class: lead invert -->

# Integrating data sources and publishing open data with fastELT & Airflow

![bg right:40% 80% fastETL logo](/slide-decks/images/fastetl.svg)

Augusto Herrmann
19.4.2023

*csv,conf,v7*

---

<!--
paginate: true
-->

# Who am I

- Augusto Herrmann – [https://herrmann.tech](herrmann.tech)
  - background in Open Data (2010-2018)
  - data engineering (2020-2023)

## Where to find this presentation

https://herrmann.tech/slide-decks/2023/04/integrating-data-sources-and-publishing-open-data-with-fastetl-and-airflow

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>  licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

---
<style scoped>
  section {
    background-image: none;
  }
</style>

# The team who made it

![](https://contributors-img.web.app/image?repo=economiagovbr/FastETL)
<div class="container">
  <div class="col">
    <ul>
      <li> <a href="https://github.com/nitaibezerra">Nitai Bezerra</a> </li>
      <li> <a href="https://github.com/edulauer">Eduardo Lauer</a> </li>
      <li> <a href="https://github.com/vitorbellini">Vitor Bellini</a> </li>
    </ul>
  </div>
  <div class="col">
    <ul>
      <li> <a href="https://github.com/washolive">Washington Oliveira</a> </li>
      <li> <a href="https://github.com/gutaors">Gustavo Silveira</a> </li>
      <li> ... and <a href="https://github.com/economiagovbr/FastETL/graphs/contributors">more </a> </li>
    </ul>
  </div>
</div>

**Data engineering team**
Secretariat for Management and Innovation
Ministry of Management and Innovation in Public Services, Brazil

---

![bg right:40% 80% fastETL logo](/slide-decks/images/fastetl.svg)

# What is it

- a free and open source plugin for Apache Airflow ![airflow icon](/slide-decks/images/airflow-icon.png)
- has features that are useful for making ETL pipelines 🛠
- speeds up the data pipeline development process 🏃


---

# Why we made it

- code we wrote had been using extensively could be useful to others who use Airflow
- we 💓 free and open source software
- expand our network of developers 👥
- get feedback and contributions 👂

---

![bg right:30% 80% Airflow logo](/slide-decks/images/airflow-logo.png)

# Our team and Airflow

[Apache Airflow](https://airflow.apache.org/) is
- free and open source software with a robust and active community
- task scheduler and orchestrator: directed acyclic graphs (DAGs)
- visibility into ETL processes and notifications: what broke, when and why

---

# How we use Airflow

and **fastETL** to

- periodically synchronize data sources in the data lake
  - sources are databases, spreadsheets (Excel, Google, Sharepoint) and others
  - data is used for analysis, auditing and to create dashboards
- publish open data on the open data portal
- notify people about publications in the official gazette ([Ro-DOU](https://github.com/economiagovbr/Ro-dou/) project)
- notifications by email and Slack
- manage sprint stories and tasks using the Trello API

---

# Why use fastETL

- fast development of data pipelines
- main features:
  - Full or incremental **replication** of tables in SQL Server, and Postgres databases (and MySQL sources)
  - Load data from **GSheets** and from spreadsheets on **Samba/Windows** networks
  - Extracting **CSV** from SQL
  - Clean data using custom data patching tasks (e.g. for messy geographical coordinates, mapping canonical values for columns, etc.)

---

# Why use fastETL

- more features:
  - Querying the Brazilian National Official Gazette's (**DOU**'s) API
  - Using a **Open Street Routing Machine** service to calculate route distances
  - Using **CKAN** or dados.gov.br's API to update dataset metadata
  - Using **Frictionless Tabular Data Packages** to write **data dictionaries** in OpenDocument Text format

---

# Example: replicating a database table

```python
t0 = DbToDbOperator(
    task_id="copy_data",
    source={
        "conn_id": airflow_source_conn_id,
        "schema": source_schema,
        "table": table_name,
    },
    destination={
        "conn_id": airflow_dest_conn_id,
        "schema": dest_schema,
        "table": table_name,
    },
    destination_truncate=True,
    copy_table_comments=True,
    chunksize=10000,
    dag=dag,
)
```

---

![bg right map visualization of TaxiGov rides](https://github.com/economiagovbr/taxigovviz/raw/main/assets/images/mapa-de-calor-taxigov.png)

<div>
  <img style="float:right; width:100px" src="/slide-decks/images/taxigov-logo.png" />

# Example use case: TaxiGov

- ride system for public officials using Taxis
- over 900k rides since 2016
- 35k+ users 
- used by 163 public organizations in federal, state and municipal governments

</div>

---

![bg left photo from above of traffic Avenida Paulista, São Paulo](/slide-decks/images/vinicius-amnx-amano-MmfCeGqNxp8-unsplash.jpg)


# TaxiGov: the data sources

- 29 heterogeneous databases with various table schemas
- 5 different suppliers
- many fields of unstructured text (motive, status, organization) – messy!

---

![bg right:50% 80% logo of TaxiGov](/slide-decks/images/taxigov-airflow-datasets.png)

# TaxiGov: the data pipelines

1. collect from the 29 data sources (starts daily at 7:45 am)
2. clean the data with **fastETL patchwork** and load it into a unified schema
3. select data with no privacy restrictions and publish it as open data (finished before 8:30 am 🕣)

---

# TaxiGov: cleaning data with patchwork

![bg left width:600px part of the pipeline: patchwork cleaning of data](/slide-decks/images/taxigov-data-pachwork.png)

**Example:** Geographical coordinates in sources have sometimes

- wrong decimal separator
- wrong signal
- values multiplied by 1,000 or 10,000
- etc. 

---

# fastETL patchwork

using **GeoPointDataCleaner**

```python
def clean_coordinates(tmp_dir: str, source: str, columns: list):
        source_config = TaxiGovPipeline.get_config(source)

        patch = DataPatch.from_file(
            file_name=os.path.join(tmp_dir, f'{source}.zip'),
            source_id=source,
            schema=source_config['schema'],
            table=source_config['table'],
            primary_keys=source_config['primary_keys'])

        logging.info('%d linhas lidas para a fonte "%s."', len(patch.df), source)
        cleaner = GeoPointDataCleaner(
            patch.df,
            source_id=source,
            schema_name=source_config['schema'],
            table_name=source_config['table'],
            primary_keys=source_config['primary_keys'],
            columns=columns)
        cleaner.clean()
        cleaner.write(tmp_dir)
```

---

![bg left contain table structure in DBeaver](/slide-decks/images/taxigov-columns-dbeaver.png)

## table metadata

read column descriptions from the database with fastETL's **TableComments**

```python
table_metadata = TableComments(
    conn_id=MSSQL_CONN_ID, schema="TAXIGOV", table="corridas"
)
df = table_metadata.table_comments
for field in schema.fields:
    if not field.description and any(df.name.isin([field.name])):
        field.description = df[df.name == field.name].iloc[0].comment
```

and record a Tabular Data Package

---

![bg right contain data dictionary containing a description of the table's columns](/slide-decks/images/taxigov-data-dict.png)

## table metadata

from Tabular Data Package

```yaml
schema:
  fields:
    - name: base_origem
      type: string
      title: Base de origem
      description: Identificação da base de dados de origem. Normalmente contém
        a sigla do Estado e um número de versão, ex. TAXIGOV_DF_3.
      constraints:
        required: true
        minLength: 10
        maxLength: 100
    - name: qru_corrida
      type: integer
      title: Código da Corrida
      description: Código que identifica a corrida unicamente dentro da base de
        origem. Não é garantida a ausência de colisão com outros identificadores
        em outras bases de origem.
      constraints:
        required: true
        minimum: 0
    - name: orgao_nome
      type: string
      title: Nome do órgão ou entidade
      description: Nome do órgão, por extenso, sem abreviações ou siglas, conforme
        consta no SIORG.
```
to data dictionary document with **fastETL**'s **DocumentTemplateToDataDictionaryOperator**

---

# TaxiGov: open data publication
<style scoped>
  section {
    background-image: none;
  }
</style>

![example workflow of a DAG in Airflow](/slide-decks/images/example-open-data-publication-pipeline.png)

---

# Using open data with Frictionless

```python
In [1]: from frictionless import Package

In [2]: package = Package("https://repositorio.dados.gov.br/seges/taxigov/v2/datapackage.yaml")

In [3]: package.resource_names
Out[3]: 
['corridas-7-dias',
 'passageiros-solicitantes',
 'corridas',
 'corridas-2017',
 'corridas-2018',
 'corridas-2019',
 'corridas-2020',
 'corridas-2021',
 'corridas-2022',
 'corridas-2023']

In [4]: df = package.get_resource("passageiros-solicitantes").to_pandas()

In [5]: df[df["nome_passageiro"].str.upper().str.startswith("AUGUSTO HERRMANN") == True]
Out[5]: 
         base_origem           nome_passageiro          nome_solicitante cpf_solicitante   ano  mes  distancia   valor  quantidade
105925  TAXIGOV_DF_1  AUGUSTO HERRMANN BATISTA  AUGUSTO HERRMANN BATISTA  ***.303.276-**  2018   11     30.735  125.65           4
111136  TAXIGOV_DF_1  AUGUSTO HERRMANN BATISTA  AUGUSTO HERRMANN BATISTA  ***.303.276-**  2018   10     26.615   97.50           3
115336  TAXIGOV_DF_1  AUGUSTO HERRMANN BATISTA  AUGUSTO HERRMANN BATISTA  ***.303.276-**  2018    9     35.175  125.07           4
134833  TAXIGOV_DF_1  AUGUSTO HERRMANN BATISTA  AUGUSTO HERRMANN BATISTA  ***.303.276-**  2018    5     33.043  112.87           3
143470  TAXIGOV_DF_1  AUGUSTO HERRMANN BATISTA  AUGUSTO HERRMANN BATISTA  ***.303.276-**  2018    3     49.065  173.81           5
```

---

# Visualizing open data

<iframe title="heat map of taxi rides on TaxiGov" width="100%" height="400" src="https://economiagovbr.github.io/taxigovviz/maps/heatmap.html"></iframe>

Available at: https://economiagovbr.github.io/taxigovviz/

---

# Where to find fastETL

https://github.com/economiagovbr/FastETL

## Installing

- add the [`apache-airflow-providers-fastetl`](https://pypi.org/project/apache-airflow-providers-fastetl/) Python package to your Airflow environment.
- or

```bash
pip install apache-airflow-providers-fastetl
```

---

# Credits

- fastETL logo by Moisés Lima
- photo by Alex Lvrs on Unsplash
- photo by Vinicius "amnx" Amano on Unsplash

---

# Contact

- data engineering team @ the Secretariat for Management and Innovation: seges.cginf@economia.gov.br
- me: https://herrmann.tech

# Questions & feedback
👆❓
