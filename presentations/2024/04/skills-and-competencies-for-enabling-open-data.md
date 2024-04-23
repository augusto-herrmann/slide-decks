---
marp: true
theme: default
style: |
  section.lead > p > em {
      color: white;
      background-color: #e47046;
      padding: 5px 20px 10px;
      font-style: normal;
  }
  section:not(.lead) {
      background-image: url('/slide-decks/images/alex-lvrs-Md6_qA-BMis-unsplash.jpg');
  }
  section:not(.lead)::before {
      content: 'Open Data Charter - IWG Call';
      position: absolute;
      bottom: 5px;
      left: 20px;
      color: black;
      height: 40px;
      text-align: left;
      padding: 1px 10px;
      background-color: #ffb84f;
      z-index: 2;
  }
  section:not(.lead)::after {
      color: white;
      background-color: black;
      opacity: 70%;
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

# Skills and Competencies for enabling Open Data
## in public administration


Augusto Herrmann
23.4.2024

---

<!--
paginate: true
-->

# Who am I

- Augusto Herrmann – [https://herrmann.tech](herrmann.tech), background:
    - Math & CS (BSc. 2004-2007)
    - KM, IT Mgt., NLP (MSc. 2009-2011)
- civil servant since 2004.
    - national open data policy (2010-2018)
    - data engineering (2020-current)

---

# Where to find this presentation

https://herrmann.tech/slide-decks/2024/04/skills-and-competencies-for-enabling-open-data

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>  licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

---

![bg right:40% wall panel with the message "co-criar"](/slide-decks/images/cocriar.jpg)

# 2010: A bottom-up open data policy

- a team of 3, build a new policy without a budget
- Dawn of the [Open Government Partnership](https://www.opengovpartnership.org/). Principles: **Transparency**, **Collaboration**, **Participation**
- Influence: Civil Servant 2.0 – Davied van Berlo (2008)
- The solution? Use the collective intelligence!

---

![bg left:45% 100% people developing the dados.gov.br openly](/slide-decks/images/2024/04/dados-gov-br-collaborative-development-1.jpg)

# 2011: A data portal [built by citizens](https://web.archive.org/web/20210116110124/http://blog.okfn.org/2012/05/10/new-brazilian-portal-dados-gov-br-made-by-citizens/)

- Anyone interested could participate
  - [processes](https://web.archive.org/web/20210116110124/http://dados.gov.br/pagina/processo-de-participacao-social-da-inda), plans and [schedule](https://web.archive.org/web/20170725090958/http://wiki.dados.gov.br/Default.aspx?Page=Agenda-do-GT&NavPath=Principais%20t%c3%b3picos) documented in the open
  - people of diverse backgrounds
  - meetings in informal places outside government premises

---

# 2012: An infrastructure for open data

![bg right:45% people developing the dados.gov.br openly](/slide-decks/images/2024/04/2enda-trilha-sustentabilidade-economica-alexandre-gomes.jpg)


- [Working groups](https://web.archive.org/web/20220704040252/https://wiki.dados.gov.br/Grupos-de-trabalho-da-INDA.ashx) for different concerns
  - [Planning and management](https://web.archive.org/web/20220704041333/https://wiki.dados.gov.br/Gestao-e-normativo.ashx)
  - [Community management, communication, and data quality](https://web.archive.org/web/20220704040254/https://wiki.dados.gov.br/Avaliacao-continuada-de-informacao-disseminada.ashx)
  - [Technology and technical competencies](https://web.archive.org/web/20220620132850/https://wiki.dados.gov.br/Tecnologia.ashx)
  - [Metadata, data modeling, ontologies, and linked data](https://web.archive.org/web/20220704040914/https://wiki.dados.gov.br/Modelagem-Metadados-Dados-e-padroes.ashx)
  - [Data licensing](https://web.archive.org/web/20220626085634/https://wiki.dados.gov.br/Produto-GT1-Levantamento-Juridico-Licenciamento-Dados-Abertos.ashx)

---

# 2016: Open Data Plans

![bg left:45% people developing the dados.gov.br openly](/slide-decks/images/2024/04/10-oficina-pda.jpeg)

- Decree 8.777: establishes an open data planning cycle that every ministry and agency must follow
- [Capacity building workshops](https://web.archive.org/web/20200717053428/http://wiki.dados.gov.br/Capacitacao-para-Elaboracao-de-Planos-de-Dados-Abertos.ashx), in just over a year:
  - over 700 have attended in-person
  - almost 1,800 attendants in online course

---

# Transition

- 2019: open data policy management transferred to Office of the Comptroller-General – "CGU" (Decree 9.903)
- 2020: Secretariat for Management and Innovation
  - Data management and data governance
  - responsible for overarching systems: data from all ministries and agencies
  - Apache Airflow for orchestrating data pipelines
    - also for Open Data where applicable!

---

# Remaining Challenges

- Data integration across national and local levels of government
- Integration of international data and developing standards
- Establish an effective feedback loop with data users
- Identifying high value data and fostering data use
- Maturity in data management and data governance
- Data anonymization
- Automatic data licensing

---

# Data integration across levels of government

- Brazil has 5,570 municipalities
  - even keeping track of every data portal URL is hard
- federated data portals: make search easier for citizens
- develop common data standards
- fostering a network of public officials across local administration for discussing and sharing experiences on open data
- leverage interested civil society groups and projects (e.g. [Querido Diário](https://queridodiario.ok.org.br/), [Frag den Staat](https://fragdenstaat.de/))

---

# International data integration and data standards

- thematic networks that share experiences and discuss data standards in specific domains
  - [GIFT](https://fiscaltransparency.net/)
  - [Open Spending](https://www.openspending.org/)
- international data standards in specific domains
  - [Linked Open Vocabularies](https://lov.linkeddata.es/dataset/lov/)
  - [Fiscal Data Package](https://specs.frictionlessdata.io/fiscal-data-package/#language)
- integrated searchable databases of international data
  - [OpenCorporates](https://opencorporates.com/) / [OpenLEIs](http://openleis.com/)
  - [EveryPolitician](http://everypolitician.org/) (discontinued)

---

# Effective feedback loop with data users

- data portals must have a feedback mechanism so data users can report errors, ask for clarification, etc.

---

# Identifying high value data and fostering data use

- Open Data Charter / Barometer / Index list of datasets are a start but not enough
- public consultations for open data plans are important but not enough
- data publishers must engage with the data using communities, e.g. in data science / data engineering forums
- participate in events such as [Open Data Day](https://opendataday.org/)
- data publishers should hold events to showcase their best data

---

# Maturity in data management and data governance

- the organization should build capacity for public officials
- the departments and people responsible for data should be defined and easy to find out
- have an established data lifecycle
- make open data updates periodic and automatic
- data should be well documented internally, this will in turn enable better documentation for open data

---

# Data anonymization

- should be treated as a security issue (risk of re-identification)
  - e.g. have an internal "red team" try do re-identify anonymized data
- omit or mask sensitive fields
- data aggregation is helpful, but care should be taken
- assess risks and document every decision

---

# Automatic data licensing

- licensing issues are complex
- depend on national copyright / database right laws
- legal analysis should be centralized, achieve an all encompassing solutions
- license choice should come automatically from the top – neither middle level officials nor developers can't be expected to deal with such complex legal issues
- usually best to use:
  - [Public Domain Mark](https://creativecommons.org/publicdomain/mark/1.0/) / [Public Domain Dedication License](https://opendatacommons.org/licenses/pddl/1-0/) / [CC-Zero](https://creativecommons.org/publicdomain/zero/1.0/)
  - [CC-Attribution](https://opendefinition.org/licenses/cc-by/) (4.0 or later)

---

# Thank you

## Contact

- data engineering team @ the Secretariat for Management and Innovation: seges.cginf@gestao.gov.br
- me: https://herrmann.tech

## Questions & feedback
👆❓ are welcome and appreciated
