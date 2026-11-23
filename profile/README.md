<div align="center">

<img src="https://raw.githubusercontent.com/connectsapowerbi/.github/main/profile/logo-connect.png" width="240" alt="Connect Informações e Tecnologia SA"/>

# Connect Informações e Tecnologia SA

**Business Intelligence & Analytics**

Desenvolvimento e governança de dashboards Power BI para apoio à decisão estratégica e operacional.

[![Governança](https://img.shields.io/badge/Guia_de_Governança-0030C5?style=for-the-badge&logo=readthedocs&logoColor=white)](https://github.com/connectsapowerbi/pbip-tools/blob/main/docs/governanca-dashboards.md)
[![Referência](https://img.shields.io/badge/Referência_Rápida-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/connectsapowerbi/pbip-tools/blob/main/docs/QUICK_REFERENCE.md)

<br/>

![Dashboards](https://img.shields.io/badge/Dashboards-45-0030C5?style=flat-square)
![Áreas](https://img.shields.io/badge/Áreas_de_Negócio-5-31C5FE?style=flat-square)
![Páginas](https://img.shields.io/badge/Páginas-288-10E99D?style=flat-square)
![Visuais](https://img.shields.io/badge/Visuais-2.357-0030C5?style=flat-square)

</div>

---

## Ecossistema

Cada área de negócio tem um workspace no Microsoft Fabric sincronizado por Git
Integration com o repositório correspondente. O `pbip-tools` centraliza
scripts, padrões técnicos, agentes de IA e os workflows de CI/CD reutilizados
por todos os repositórios de dashboard.

```mermaid
flowchart LR
    subgraph FABRIC["Microsoft Fabric"]
        direction TB
        WSA["Workspace Analítico"]
        WSC["Workspace Campanhas"]
        WSR["Workspace Central de Relacionamento"]
        WSE["Workspace Executivo"]
        WSP["Workspace Produtos"]
        LH[("Lakehouse")]
    end

    subgraph GIT["GitHub — connectsapowerbi"]
        direction TB
        RA["analitico"]
        RC["campanhas"]
        RR["central-de-relacionamento"]
        RE["executivo"]
        RP["produtos"]
        RL["fabric-lakehouse"]
        RT[["pbip-tools"]]
    end

    WSA <-->|Git Integration| RA
    WSC <-->|Git Integration| RC
    WSR <-->|Git Integration| RR
    WSE <-->|Git Integration| RE
    WSP <-->|Git Integration| RP
    LH <-->|Git Integration| RL

    RT -.->|padroes, CI/CD, docs| RA
    RT -.->|padroes, CI/CD, docs| RC
    RT -.->|padroes, CI/CD, docs| RR
    RT -.->|padroes, CI/CD, docs| RE
    RT -.->|padroes, CI/CD, docs| RP

    style RT fill:#0030C5,color:#ffffff,stroke:#0030C5
    style LH fill:#EFF3FD,color:#0030C5,stroke:#0030C5
```

`main` é o estado publicado de cada repo — todo push nessa branch dispara o
deploy via GitHub Actions para o workspace Fabric da área (`dev` → `hml` →
`main`).

---

## Repositórios

| Repositório | Área | Camada | Dashboards |
|-------------|------|--------|:----------:|
| [**analitico**](https://github.com/connectsapowerbi/analitico) | Comercial | Report + Semantic Model | 11 |
| [**campanhas**](https://github.com/connectsapowerbi/campanhas) | Gestão de Produtos Serasa | Report + Semantic Model | 20 |
| [**central-de-relacionamento**](https://github.com/connectsapowerbi/central-de-relacionamento) | Central de Relacionamento | Report + Semantic Model | 2 |
| [**executivo**](https://github.com/connectsapowerbi/executivo) | Diretoria | Report + Semantic Model | 6 |
| [**produtos**](https://github.com/connectsapowerbi/produtos) | Comercial | Report + Semantic Model | 6 |
| [**fabric-lakehouse**](https://github.com/connectsapowerbi/fabric-lakehouse) | Data Engineering | Lakehouse / Warehouse | — |
| [**pbip-tools**](https://github.com/connectsapowerbi/pbip-tools) | Ferramentas | Scripts, CI/CD e docs compartilhados | — |

---

<div align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Microsoft Fabric](https://img.shields.io/badge/Microsoft%20Fabric-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0030C5?style=flat&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)

</div>
