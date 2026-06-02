# 📊 Análise Financeira Zoop

<p align="center">
  <img src="./Assets/painel-receita.png" alt="Dashboard Receita Zoop" width="100%">
</p>

<p align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Advanced-blue?style=for-the-badge)
![Business Intelligence](https://img.shields.io/badge/Business%20Intelligence-Analytics-success?style=for-the-badge)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Finance-orange?style=for-the-badge)

</p>

## 📌 Sobre o Projeto

Dashboard financeiro desenvolvido durante o curso **Power BI: Análises Avançadas com DAX**, da Alura.

O objetivo do projeto foi construir uma solução analítica para monitoramento de receita, permitindo acompanhar o desempenho financeiro da empresa fictícia **Zoop Megastore**, com foco especial em:

- 📈 Evolução da receita ao longo do tempo;
- 🌐 Participação do canal de vendas Online;
- 💰 Impacto das vendas realizadas com descontos superiores a 15%;
- 📊 Comparação entre receita atual e períodos anteriores;
- 🎯 Identificação de tendências de crescimento.

---

## 🚀 Dashboard Principal

### Painel Receita

O dashboard central reúne indicadores estratégicos para análise financeira e acompanhamento de performance.

### KPIs Disponíveis

| Indicador | Objetivo |
|------------|------------|
| Receita Atual | Receita total do período selecionado |
| Receita Anterior | Comparação com o período anterior |
| % Participação na Receita | Representatividade da seleção atual |
| Receita Atual da Seleção | Receita considerando os filtros aplicados |
| Vendas Canal Online | Receita proveniente do canal online |
| Vendas com +15% de Desconto | Receita gerada por vendas com descontos agressivos |

### Recursos Interativos

✅ Filtro por Ano

✅ Filtro por Segmento

✅ Filtro por Região

✅ Comparação temporal automática

✅ Indicadores dinâmicos

---

## 📈 Principais Insights do Dashboard

O painel permite responder perguntas de negócio como:

- Qual foi o crescimento da receita em relação ao ano anterior?
- Quanto do faturamento é gerado pelo canal online?
- Qual o impacto financeiro das vendas com descontos acima de 15%?
- Quais períodos apresentaram maior crescimento ou retração?
- Como a receita se comporta entre regiões e segmentos?

---

## 🧠 Técnicas DAX Aplicadas

Durante o desenvolvimento do projeto foram utilizadas funções avançadas para manipulação de contexto e inteligência temporal.

### Inteligência Temporal

```DAX
SAMEPERIODLASTYEAR()
```

Comparação automática entre períodos equivalentes de anos diferentes.

### Manipulação de Contexto

```DAX
CALCULATE()
ALL()
```

Alteração e remoção de filtros para construção de métricas analíticas.

### Cálculos Percentuais

```DAX
DIVIDE()
```

Criação de indicadores percentuais com tratamento seguro de divisões.

### Filtros Dinâmicos

```DAX
CALCULATE(
    [Vendas Ano Corrente],
    DimChannel[Channel] = "Online"
)
```

Segmentação de métricas por regras de negócio.

---

## 📊 Principais Medidas Desenvolvidas

### Receita Atual

```DAX
Receita Ano Atual =
CALCULATE(
    [Vendas Ano Corrente],
    ALL(DimCustomer)
)
```

### Receita Ano Anterior

```DAX
Receita Ano Passado =
CALCULATE(
    [Vendas Ano Corrente],
    SAMEPERIODLASTYEAR(dCalendario[Date]),
    ALL(DimCustomer)
) + 0
```

### Participação na Receita

```DAX
Percentual Filial =
DIVIDE(
    [Vendas Ano Corrente],
    [Receita Ano Atual]
)
```

### Receita Canal Online

```DAX
Total Vendas Online =
CALCULATE(
    [Vendas Ano Corrente],
    DimChannel[Channel] = "Online"
)
```

### Receita com Desconto Superior a 15%

```DAX
Total Vendas Acima 15 =
CALCULATE(
    [Vendas Ano Corrente],
    FactSales[DiscountPct] > 0.15
)
```

### Crescimento da Receita

```DAX
Percentual Crescimento =
IF(
    DIVIDE(
        [Vendas Ano Corrente] - [Receita Ano Passado],
        [Receita Ano Passado]
    ) > -1,
    DIVIDE(
        [Vendas Ano Corrente] - [Receita Ano Passado],
        [Receita Ano Passado]
    ),
    BLANK()
)
```

---

## 🏗️ Estrutura do Projeto

```text
Analise-Financeira-Zoop
│
├── Dados
│   └── zoop-dataset.csv
│
├── Power BI
│   └── analise-financeira-zoop.pbix
│
├── assets
│   └── painel-receita.png
│   └── painel-receita.mp4
│
└── README.md
```

---

## 🎯 Competências Demonstradas

- Power BI
- DAX Avançado
- Business Intelligence
- Data Analytics
- Modelagem de Dados
- KPIs Financeiros
- Inteligência Temporal
- Storytelling com Dados
- Dashboards Interativos
- Análise de Receita

---

## 📚 Curso

Projeto desenvolvido durante o curso:

**Power BI: Análises Avançadas com DAX** — Alura

---

## ⚠️ Observação

Os dados utilizados neste projeto são fictícios e foram disponibilizados exclusivamente para fins educacionais durante o curso.

---

## 👨‍💻 Autor

**Vinicius Cunha**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/viniciuscunhadata)

[![GitHub](https://img.shields.io/badge/GitHub-Repositório-black?style=for-the-badge&logo=github)](https://github.com/vcbonani)
