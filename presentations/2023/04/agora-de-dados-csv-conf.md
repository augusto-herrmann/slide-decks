---
marp: true
theme: default
style: |
  /* fira-sans-regular - latin */
  @font-face {
    font-display: swap; /* Check https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display for other options. */
    font-family: 'Fira Sans';
    font-style: normal;
    font-weight: 400;
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.eot'); /* IE9 Compat Modes */
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.woff2') format('woff2'), /* Super Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.woff') format('woff'), /* Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-regular.svg#FiraSans') format('svg'); /* Legacy iOS */
  }

  /* fira-sans-italic - latin */
  @font-face {
    font-display: swap; /* Check https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display for other options. */
    font-family: 'Fira Sans';
    font-style: italic;
    font-weight: 400;
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.eot'); /* IE9 Compat Modes */
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.woff2') format('woff2'), /* Super Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.woff') format('woff'), /* Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-italic.svg#FiraSans') format('svg'); /* Legacy iOS */
  }

  /* fira-sans-600 - latin */
  @font-face {
    font-display: swap; /* Check https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display for other options. */
    font-family: 'Fira Sans';
    font-style: normal;
    font-weight: 600;
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.eot'); /* IE9 Compat Modes */
    src: url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.woff2') format('woff2'), /* Super Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.woff') format('woff'), /* Modern Browsers */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.ttf') format('truetype'), /* Safari, Android, iOS */
        url('/assets/fonts/fira-sans/fira-sans-v16-latin-600.svg#FiraSans') format('svg'); /* Legacy iOS */
  }

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
    content: 'Ágora de dados – csv,conf,v7';
    position: absolute;
    bottom: 5px;
    left: 20px;
    color: black;
    height: 40px;
    text-align: left;
    font-weight: bold;
    padding: 5px 0 5px 0px;
    z-index: 2;
  }
  section:not(.lead)::after {
    color: black;
    background: rgb(250,240,213);
    background: linear-gradient(0deg, rgba(250,240,213,1) 0%, rgba(250,240,213,1) 20%, rgba(255,255,255,1) 100%);
    bottom: 0;
    right: 0;
    width: 100%;
    height: 60px;
    line-height: 2.5em;
    padding: 5px 20px 0 0;
    text-align: right;
    z-index: 1;
  }
  section.day h1 {
    font-size: 48pt;
    text-align: center;
  }
  .container {
    display: flex;
  }
  .col {
    flex: 1;
  }
---

<!-- _class: lead invert -->

# Ágora de dados

*csv,conf,v7*

19-20.4.2023

> **Local:** Novotel 🏨
> Avenida Corrientes, 1.334 [📍](](https://www.openstreetmap.org/node/4683530377#map=17/-34.60384/-58.38492))
> Buenos Aires, 🇦🇷

---

<!--
paginate: true
-->

# csv,conf

> é um evento para a comunidade de **criadores e gestores de dados**
> de todo o mundo. No csv,conf, nos reunimos para discutir dados abertos, e
> como os **dados** podem ser usados para **resolver problemas** através de
> 
> - código aberto,
> - jornalismo,
> - ciência,
> - governo,
>
> e muito mais!

---

# csv,conf

> é uma conferência **organizada pela comunidade** que vai além dos
> valores separados por vírgulas: reúne um grupo diversiﬁcado para
> discutir temas como
> - compartilhamento de dados,
> - ética de dados,
> - análise de dados
> 
> entre muitos outros.

---

## patrocinadores

a `csv,conf` é organizada pela comunidade, mas algumas empresas patrocinam o evento. Nesa edição:

<div class="container">
  <div class="col">
    <ul>
      <li> Alfred P. Sloan Foundation </li>
      <li> R Consortium </li>
      <li> OpenNews </li>
    </ul>
  </div>
  <div class="col">
    <ul>
      <li> Omidyar Network </li>
      <li> Lincoln Loop </li>
      <li> Chan Zuckerberg Initiative </li>
      <li> DataCite </li>
    </ul>
  </div>
</div>


---

## edições anteriores

![bg right:40% foto da comma llama na csv,conf em 2017](/slide-decks/images/2023/04/comma-llama-1.jpg)

- em **Berlim** 🇩🇪, **Portland** 🇺🇸 e **[online](https://csvconf.com/2021/)** 🌐
- v7 é a primeira vez no hemisfério sul 🌎
- mascote: `#commallama` 🦙 (foto de 2017)
- palestras gravadas 📼 no [YouTube](https://www.youtube.com/channel/UCWq7JfT4PJrCZLmxSOVJOww)
  - em breve as da v7 também

---

## “pega-lhamas”

![bg left pega-bichinhos com lhamas de pelúcia](/slide-decks/images/2023/04/llama-catcher.jpg)

- “Lhama Vírgula” ou “comma llama”
- lhamas variadas produzidas por artistas locais
- grátis!

---

## estrutura do evento

![bg right sala de "data tables"](/slide-decks/images/2023/04/csv-conf-data-tables.jpg)

- 3 salas simultâneas (A, B, C)
- 1 sala para atividades espontâneas: *“data tables”* (D)
- as *keynotes*
  - antes e depois do almoço
  - salas (A, B, C) ajuntadas em uma

---

<!--
_class: lead day invert
-->

# dia 19

---

## Opening up African Data

![bg left:65% Tricia faz sua apresentação](/slide-decks/images/2023/04/csv-conf-tricia.jpg)
![bg MapMakoko](/slide-decks/images/2023/04/csv-conf-code-for-africa.jpg)

Tricia Govindasamy

- atividades da *Code for Africa* ![w:50 logo da Code for Africa](/slide-decks/images/2023/04/code-for-africa-logo.png)
- repositório colaborativo de dados abertos [openAFRICA](https://openafrica.net/)
- *fact checking* colaborativo

---

## no mesmo horário 🕤 (9:25)

![bg right:30% William apresenta Dashbuilder](/slide-decks/images/2023/04/csv-conf-dashbuilder.jpg)

- Virus discovery at a global scale – Humberto Debat
- Agile Data Visualization with **Dashbuilder** – William Antônio Siqueira 🇧🇷 (Red Hat)

---

## Frictionless Application (IDE para CSV)

![bg left:40% Evgeny apresenta Frictionless Application](/slide-decks/images/2023/04/csv-conf-frictionless-application.jpg)

Evgeny Karev ([apresentação](https://docs.google.com/presentation/d/1VEVBCnxAouNXA0jEcyCjrXtx2R_t-QmFzSZCp3UlqD8/edit#slide=id.gfaff7fb3b5_0_203))

- ferramenta gráfica para editar tabelas
- validação de dados, editar esquemas
- gerar Tabular Data Packages
- visualização de dados
- storytelling de dados com LiveMark
- publicar no ![CKAN](/slide-decks/images/ckan.svg)

---

## no mesmo horário 🕙 (9:50)

- #Menstruacción: How much does it cost to menstruate? – Laia Domenech Burin
- Baking bread on Sundays makes me happy – Juan De Dios Santos

---

## From garbage data to data on garbage

![bg right:30% tela do "dónde reciclo"](/slide-decks/images/2023/04/donde-reciclo.png)

Daniel Carranza

- co-fundador do [DATA Uruguay](https://data.org.uy/)
- [dónde reciclo](https://dondereciclo.uy/)
  - site e app para localizar pontos de reciclagem
  - no Uruguai e na Colômbia
  - usa dados abertos e software livre

---

## no mesmo horário

![bg left:60% palestra da LLEAD / IPNO](/slide-decks/images/2023/04/csv-conf-police-misconduct-database.jpg)

- Investigating police misconduct and migratory patterns – Rajiv Sinclair e Ayyub Ibrahim
- Building Digital Democracy Solutions in Kenya through Data
Tricia Govindasamy

---

## KEYNOTE - Collective Creation of Open Science – Laura Acion

![bg right palestra da LLEAD / IPNO](/slide-decks/images/2023/04/csv-conf-keynote-open-science.jpg)

- rede colaborativa de ciência aberta
- comunidade R, compartilhamento de código
- compartilhamento de datasets
- reproducibilidade de pesquisas

---

## KEYNOTE - How To Cultivate A Sustainable Open-Source Ecosystem (OSE) – Karthik Ram

- análise dos ecossistemas de software livre
  - eixo: quantidade de desenvolvedores
  - eixo: quantidade de usuários
- dinâmica entre os quadrantes
- Software Bill of Materials – SBOM

---

## Integrating data sources and publishing open data with FastELT & Airflow
Augusto Herrmann ([apresentação](https://herrmann.tech/slide-decks/2023/04/integrating-data-sources-and-publishing-open-data-with-fastetl-and-airflow))

![bg right:40% 80% fastETL logo](/slide-decks/images/fastetl.svg)

---

## no mesmo horário 🕝 (14:30)

![bg right palestra "Nothing about us"](/slide-decks/images/2023/04/csv-conf-nothing-abous-us.jpg)

- Data Management on the Front Lines: Managing Administrative Data at the Source – Kelsey Badger
- Nothing about us, without us: Participatory approaches to make data by the people for the people – Bastian Greshake Tzovaras

---

## Miller: a swiss-army chainsaw for CSV and more

![bg left:60% palestra ferramenta Miller tabelas na linha de comando](https://github.com/johnkerl/miller/raw/main/docs/src/coverart/cover-combined.png)

John Kerl

> Miller is like awk, sed, cut, join, and sort for data formats such as CSV, TSV, JSON, JSON Lines, and positionally-indexed.

---

- ferramenta de linha de comando para trabalhar com CSVs
- selecionar linhas, colunas, transformar, cortar,etc.
- encadear como se faz com *pipes* na CLI

### Instalação

```bash
apt-get install miller
```

---

## no mesmo horário 🕒 (14:55)

![bg right palestra The Carpentries Toolkit](/slide-decks/images/2023/04/csv-conf-carpentries.jpg)

- Open Data on Funding for Open Infrastructure Services – Tania L. Hernandez Ortiz ([apresentação](https://shorturl.at/jyBI9))
- csv,conf Community Building with The Carpentries Toolkit of IDEAS – Kari L. Jordan, PhD

---

## Land use trajectories as text data

Germán Rosati

- informações de satélite sobre uso da terra
  - vegetação nativa, agricultura, urbana, etc.
  - série temporal
- a sequência temporal é considerada como uma palavra
  - distância de edição de texto ([Levenshtein](https://en.wikipedia.org/wiki/Levenshtein_distance))
  - clustering a partir da matriz de distâncias
- identifica ocupações recentes da terra, alterações de uso

---

## no mesmo horário 🕞 (15:20)

- Towards a Community-Based Responsible Use of Health Data in Argentina and beyond – Sabrina Laura López
- Criminal AI - Surveillance, Wage Theft & Forced Labor in a Time of Machine Learning – Adrienne Williams

---

## Narrative Expansion: Decolonising Development

Florence Akara

- trabalho educativo nas escolas da Tanzania
- descolonização: procurar desfazer os efeitos da colonização europeia
- educação sobre o início menstruação
  - oposição da cultura tradicional em algumas culturas
  - melhores resultados quando inclui também os meninos
  - pais têm preocupações com os custos

---

## no mesmo horário 🕓 (16:10)

- A map manager that promotes open standards and technological sovereignty for research in Mexico – Yosune Chamizo Alberro
- Trust but verify: combining GPTs and CRDTs to empower researchers and deter fraudsters – Nokome Bentley

---

## Identifying DDoS attacks on IoT devices using deep learning

Deborah Mesquita 🇧🇷

- estudou segurança em equipamentos de IoT
- usou um equipamento barato (30 reais) e fácil de se programar
- tráfego legítimo misturado com ataques DoS
- features para treino: cabeçalhos no nível de transporte (TCP e UDP)
- conseguiu resultados satisfatórios (> 80%) com pouco esforço

---

## no mesmo horário 🕟 (16:35)

- What are you? Automating journal subject classification – Esha Datta
- Lecturers Without Borders: creating opportunities for science outreach – Eugenia Covernton

---

## recepção no Sky Bar

![bg left:65% vista do alto do Jousten Hotel](/slide-decks/images/2023/04/csv-conf-skybar-1.jpg)
![bg pessoas na recepção](/slide-decks/images/2023/04/csv-conf-skybar-2.jpg)
![bg mais pessoas na recepção](/slide-decks/images/2023/04/csv-conf-skybar-3.jpg)

- local: Jousten Hotel [📍](https://www.openstreetmap.org/node/7111373185#map=15/-34.6036/-58.3649)
- Buenos Aires vista do alto
- *networking*
- cortesia da Code for Science & Society

---

<!--
_class: lead day invert
-->

# dia 20

---

## Datasets Have Worldviews: Understanding Classification In Your Data

Dylan Baker

- categorias de classificação nunca são “neutras”
- [escala Fitzpatrick](https://en.wikipedia.org/wiki/Fitzpatrick_scale) de tons de pele

---

## no mesmo horário 🕘 (9:00)

![bg right apresentação Querido Diário](/slide-decks/images/2023/04/csv-conf-querido-diario.jpg)

- Open research needs open (meta)data – Gabriela Mejias e Mary Hirsch
- Querido Diário: how an open source project is freeing official municipal records for 45 million people in Brasil (and counting!) – Fernanda Campagnucci 🇧🇷

---

## How to find clues for your research in hundreds of datasets using Aleph

Mariel Fritz Patrick e David Gonzalez

- ferramenta para organizar e indexar diversas fontes de dados
  - inclusive leitura ótica de documentos PDF!
- reconhecimento de entidades
- raspar sites
- cruzamento de dados
- jornalismo de dados e investigações de corrupção (Organized Crime and Corruption Reporting Project – [OCCRP](https://www.occrp.org/en))

Veja meu [texto sobre o Aleph](https://dadosabertos.social/t/aleph-uma-ferramenta-para-seguir-fluxos-de-dinheiro/249).

---

## no mesmo horário 🕤 (9:25)

![bg left apresentação UK data](/slide-decks/images/2023/04/csv-conf-uk-open-data.jpg)

- Supporting data integration and usability to advance environmental and climate justice – Katie Hoeberling
- UK government: Building better data for a better future – Darren Barnes
  - Office for National Statistics pretende publicar todos os seus dados como CSV-W

---

## Lessons from the history of literacy

Salina Cheuk Ting Ho

- como a alfabetização ou letramento evoluiu na história
  - ampla alfabetização é algo recente
  - leitura e escrita historicamente eram ensinadas separadamente
- dificuldade em “vender” a ideia que as pessoas precisam aprender sobre dados

---

## no mesmo horário 🕙 (9:50)

![bg right apresentação solving childhood dementia](/slide-decks/images/2023/04/csv-conf-childhood-dementia.jpg)

- Constructing a Visual Dataset to Study the Effects of Spatial Apartheid in South Africa – Raesetje Sefala
- Solving Childhood Dementia: When data isn't enough – Sarah Catherine Baker

---

## OpenAQ: Wrangling the world's air quality data

Russ Biggs

- dados coletados de estações metereológicas
  - estações custam muito caro
- padronização dos dados
- visualização em mapa
- séries temporais
- “buracos” espaciais onde não há dados

---

## no mesmo horário (10:15)

![bg left apresentação quebra-cabeças identidade celular](/slide-decks/images/2023/04/csv-conf-jigsaw-cell-identity.jpg)

- A community driven initiative to crowdsource background details of 1700 High Court Judges in India – Apoorv Anand
- The Jigsaw Puzzle of Cellular Identity – Kevin MacPherson

---

## KEYNOTE - Giuseppe Sollazzo - Talking with data – stories and lessons from my data adventures

- UK Open Data User Group – ODUG
- governo do Reino Unido
- feedback para as perguntas dos usuários de dados é importante
- Parli-N-Grams

---

## KEYNOTE - Alex Hanna - Shifting the Frame: The Labors of ImageNet and AI Data

![bg contrast:50% saturate:0.5 opacity:0.3 palestra magna da Alex Hanna](/slide-decks/images/2023/04/csv-conf-alex-hanna.jpg)

> pesquisadora estadunidense transgênero, especializada em ética em
> inteligência artificial. Dirige o instituto de pesquisa DAIR. Doutora
> em Sociologia pela Universidade Wisconsin-Madison. Utilizou ferramentas
> computacionais para analisar movimentos sociais no Egito. Foi
> pesquisadora sênior no Google, do qual saiu com críticas à cultura
> tóxica da empresa. ([Wikipédia](https://pt.wikipedia.org/wiki/Alex_Hanna))

- ImageNet é o dataset anotado mais usado para visão computacional
- classificação baseada no WordNet
- codificação de preconceitos na categorização
- categorizações são sempre políticas!

---

## podcast Pizza de Dados

- gravamos um episódio Pizza na Estrada
  - com Ana Cecília (hostess), Fernanda Campagnucci e eu
- ainda não foi ao ar
  - quando for, será no [canal no YouTube](https://www.youtube.com/c/pizzadedados) do Pizza de Dados

---

## Resources and challenges for building global equitable open science communities

![bg right apresentação OLS Open Seeds](/slide-decks/images/2023/04/csv-conf-open-seeds.jpg)

Paz Bernaldo

- [programa](https://openlifesci.org/) da Open Life Science
- formar redes de pares entre pesquisadora(e)s
- embaixadora(e)s da ciência aberta

---

## Tell me who you hang out with and I'll tell you who you are: a collaborative analysis using social network analysis

Yanina Noemí Bellini Saibene

- análise de redes de pesquisadores
- relacionamento: publicação conjunta
- conectividade de grafos:
  - grau do nó
  - clusters, etc.
- achar os nós “centrais” de cada rede

---

## Procurement data: where to find it and how to use it

![bg left w:100% apresentação OLS Open Seeds](/slide-decks/images/2023/04/open-contracting.png)

Félix Pedro Penna

- Fiscal Data Package (Frictionless, Banco Mundial e [GIFT](https://fiscaltransparency.net/))
- [Open Contracting Partnership](https://www.open-contracting.org/)
  - Open Contracting Data Standard
  - ausência no mapa!


---

# O que foi bom

- palestras de altíssimo nível 💯
- conhecer pessoalmente quem só via no virtual

# O que foi ruim

- que acabou! 😢

# Vídeos

Em breve estarão disponíveis no [canal no YouTube](https://www.youtube.com/channel/UCWq7JfT4PJrCZLmxSOVJOww) da csv,conf.

- 👉 lembrar de assistir! 👀

---

# Créditos

- fotos do evento compartilhadas pelos participantes, em especial Yani Bellini
- foto da `#commallama`: divulgação csv,conf 2017
- foto do pega-lhamas: Fernanda Campagnucci
- logo do fastETL por Moisés Lima
- foto por Alex Lvrs on Unsplash
- imagens de tela do Dónde Reciclo e Miller
- mapa no site da Open Contracting Partnership
- apresentação feita [em Markdown](https://github.com/augusto-herrmann/slide-decks/blob/main/presentations/2023/04/agora-de-dados-csv-conf.md) usando [Marp](https://marp.app) por Yuki Hattori

