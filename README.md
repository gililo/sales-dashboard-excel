# 📊 Sales Dashboard

> Transformando dados brutos em informações visuais claras e úteis para análise eficaz do desempenho de vendas e tomada de decisões baseadas em dados.



## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Objetivo](#objetivo)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Base de Dados](#base-de-dados)
- [Manipulação dos Dados](#manipulação-dos-dados)
- [Como Executar](#como-executar)
- [Funcionalidades](#funcionalidades)
- [Visualizações](#visualizações)
- [Contribuição](#contribuição)



## 🧩 Sobre o Projeto

Este projeto consiste em um **dashboard interativo de vendas**, proposto por um Desafio da DIO e desenvolvido para facilitar a interpretação de dados comerciais. A partir de uma base de dados estruturada, o sistema processa e apresenta as informações de forma visual, intuitiva e acionável.



## 🎯 Objetivo

Transformar dados brutos de vendas em informações visuais claras e úteis, permitindo:

- 📈 Análise eficaz do **desempenho de vendas**
- 🔍 Identificação de **tendências e padrões**
- ✅ **Tomada de decisões** baseadas em dados concretos
- 📊 Monitoramento de **KPIs e metas comerciais**



## 🛠️ Tecnologias Utilizadas

| Tecnologia / Recurso | Descrição |
|----------------------|-----------|
| **Microsoft Excel** | Ferramenta principal para construção do dashboard |
| **Power Query** | Tratamento, transformação e enriquecimento dos dados |
| **Tabelas Dinâmicas** | Agregação e sumarização dos dados para os gráficos |
| **Gráficos Dinâmicos** | Visualizações interativas conectadas às Tabelas Dinâmicas |
| **Segmentadores (Slicers)** | Filtros interativos por Região, Loja e Categoria |



## 📁 Estrutura do Projeto

```
📦 sales-dashboard
├── 📊 dashboard-sales.xlsx        # Base de dados original
└── 📊 dashboard-sales-final.xlsx  # Versão final com transformações Power Query + os dashboards prontos
```



## 🗄️ Base de Dados

A base de dados do projeto está contida diretamente no arquivo:

```
dashboard-sales.xlsx
```

O arquivo Excel serve como fonte principal dos dados, centralizando todas as informações de vendas que alimentam o dashboard.

### 📌 Campos da Base de Dados Original

| Campo | Descrição |
|-------|-----------|
| `Order_ID` | Identificador único do pedido |
| `Date` | Data da venda |
| `Day_of_Week` | Dia da semana da venda |
| `Shift` | Turno em que a venda foi realizada |
| `Store_ID` | Identificador único da loja |
| `Store_Name` | Nome da loja |
| `City` | Cidade da loja |
| `State` | Estado da loja |
| `Region` | Região geográfica |
| `Category` | Categoria do produto |
| `Product` | Nome do produto |
| `Quantity` | Quantidade vendida |
| `Unit_Price` | Preço unitário do produto |
| `Gross_Revenue` | Receita bruta da venda |
| `Discount_Amount` | Valor do desconto aplicado |
| `Net_Revenue` | Receita líquida (após descontos) |
| `Cost_Of_Goods_Sold` | Custo dos produtos vendidos (CPV) |
| `Gross_Profit` | Lucro bruto |
| `Sales_Channel` | Canal de venda (ex: online, físico) |
| `Payment_Method` | Método de pagamento utilizado |
| `Customer_Satisfaction` | Índice de satisfação do cliente |



## 🔧 Manipulação dos Dados

Antes de alimentar o dashboard, a base de dados passou por uma etapa de **tratamento** utilizando o **Power Query** do Excel (`Obter e Transformar Dados > De Tabela/Intervalo`), garantindo consistência e criando campos auxiliares para as análises.

### ➕ Campos Calculados / Derivados

| Campo | Origem | Descrição |
|-------|--------|-----------|
| `Quarter` | `Date` | Trimestre extraído da data da venda (Q1, Q2, Q3, Q4) |
| `Discount_Tier` | `Discount_Amount`, `Gross_Revenue` | Taxa de desconto calculada (`Discount_Amount / Gross_Revenue`), arredondada para 1 casa decimal |
| `Shift_Desc` | `Shift` | Descrição do turno, obtida ao dividir a coluna `Shift` por delimitador de espaço |



## ▶️ Como Executar

1. Faça o download ou clone este repositório
2. Abra o arquivo `dashboard-sales-final.xlsx` no **Microsoft Excel**
3. Navegue entre as páginas **Region View** e **Stores & Categories** pelos botões no canto superior direito
4. Utilize os **segmentadores (slicers)** laterais para filtrar os dados por Região, Loja ou Categoria



## ✨ Funcionalidades

- 🔀 **Navegação entre páginas** — alternância entre Region View e Stores & Categories via botões
- 🎛️ **Filtros interativos** — segmentadores por Região (página 1), Loja e Categoria (página 2)
- 📊 **KPIs dinâmicos** — indicadores de Orders, Gross Revenue, Discount, Net Revenue, Gross Profit e Gross Profit Margin % que atualizam conforme os filtros
- 📈 **Gráficos dinâmicos** — todos os gráficos respondem aos slicers em tempo real
- 🏆 **Top N fixo** — ranking de Top 3 Stores e Top 2 Categories por Gross Profit, independente dos filtros aplicados



## 📊 Visualizações

O dashboard é composto por **2 páginas** navegáveis, com identidade visual baseada nas cores oficiais do McDonald's (vermelho e dourado).

### 📄 Page 1 — Region View

Visão financeira geral com filtro por **Região**.

| Elemento | Descrição |
|----------|-----------|
| **KPIs em destaque** | # Orders, Gross Revenue, Coupons Discount, Net Revenue, Gross Profit e Gross Profit Margin % |
| **Gráfico de barras + linha** | Gross Revenue mensal (barras) vs Gross Profit Margin % (linha), de Jan a Dez |
| **Tabela financeira mensal** | Fluxo Gross Revenue → Discount → Net Revenue → COGS → Gross Profit, com barras proporcionais por mês |

### 📄 Page 2 — Stores & Categories

Visão de performance por loja, categoria, turno, canal e satisfação, com filtros por **Loja** e **Categoria**.

| Elemento | Descrição |
|----------|-----------|
| **Top 3 Stores** | Ranking fixo das 3 lojas com maior Gross Profit (não afetado pelos slicers) |
| **Top 2 Categories** | Ranking das 2 categorias com maior Gross Profit |
| **Gross Profit by Shifts** | Barras horizontais ordenadas do maior para o menor turno (Afternoon, Overnight, Morning, Evening) |
| **Gross Profit by Channels** | Barras horizontais por canal de venda (Uber Eats, Drive-Thru, DoorDash, Self-Service Kiosk, McDonald's App, Counter) |
| **Customer Satisfaction by Orders** | Barras horizontais com ícones de estrelas (1 a 5), mostrando volume de pedidos por nota de satisfação |



## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma *issue* ou enviar um *pull request*.

---

<p align="center">
  Desenvolvido com 💙 para análise inteligente de dados
</p>
