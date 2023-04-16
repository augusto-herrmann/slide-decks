---
marp: true
theme: default
style: |
  body {
    font-family: 'Fira Sans';
  }
  section:not(.lead)::before {
    content: 'csv,conf,v7';
    position: absolute;
    bottom: 5px;
    left: 20px;
    color: white;
    width: 95%;
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

- a free and open source plugin for Apache Airflow
- has features that are useful for making ETL pipelines
- speeds up the data pipeline development process


---

# Why we made it

- code we wrote had been using extensively could be useful to others who use Airflow
- we 💓 free and open source software
- expand our network
- get feedback and contributions

---

![bg right:30% 80% Airflow logo](/slide-decks/images/airflow-logo.png)

# Our team and Airflow

[Apache Airflow](https://airflow.apache.org/) is
- free and open source software with a robust and active community
- task scheduler and orchestrator: directed acyclic graphs (DAGs)
- visibility into ETL processes and notifications: what broke, when and why

---

# How we use Airflow

- periodically synchronize data sources in the data lake
  - sources are databases, spreadsheets (Excel, Google, Sharepoint) and others
  - data is used for analysis, auditing and to create dashboards
- publish open data on the open data portal
- notify people about publications in the official gazette ([Ro-DOU](https://github.com/economiagovbr/Ro-dou/) project)
- notifications by email and Slack
- manage sprints using the Trello API

---


# Example of an open data publication pipeline

![example workflow of a DAG in Airflow](/slide-decks/images/example-open-data-publication-pipeline.png)

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
  - Using **Frictionless Tabular Data Packages** to write OpenDocument Text format **data dictionaries**


