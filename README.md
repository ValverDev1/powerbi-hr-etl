# Power BI – ETL de RH e Risco de Demissão

Meu primeiro projeto de portfólio em Power BI, focado em **ETL (Extract, Transform, Load)** e criação de uma coluna condicional para estimar o **Risco de Demissão** de funcionários com base em sua satisfação no trabalho.

## 🎯 Objetivo do Projeto

Simular o trabalho de um analista de dados de RH que precisa:
- Limpar e padronizar uma base grande de funcionários.
- Criar uma lógica simples de **risco de demissão** para apoiar decisões de retenção de talentos.

## 🧠 Pergunta de Negócio

> “Quais funcionários apresentam maior risco de demissão, de acordo com o nível de satisfação no trabalho?”

Este projeto é uma primeira versão, focada em aprender ETL e regras condicionais.

## 🗂️ Dataset

- Fonte: Dataset de Recursos Humanos (base pública, exemplo usado em estudos de Analytics).
- Contém informações como:
  - Satisfação no trabalho (`JobSatisfaction`)
  - Renda mensal (`MonthlyIncome`)
  - Departamento (`Department`)
  - Atributos demográficos e de trabalho (idade, cargo, tempo de empresa, etc.)

## 🔄 Processo de ETL no Power BI

Todo o processo foi feito no **Power Query Editor** do Power BI:

1. **Importação dos dados**
   - `Obter dados` → Excel → seleção da aba principal de funcionários.
   - Abertura no Power Query para aplicação das transformações.

2. **Limpeza de dados**
   - Remoção de linhas com `MonthlyIncome = 0` (valores inválidos).
   - Verificação e ajuste de tipos de dados (número, texto, etc.) quando necessário.

3. **Padronização de campos**
   - Coluna `Department`:
     - `Sales` → `Vendas`
     - `Research & Development` → `P&D`
     - `Human Resources` → `Recursos Humanos`

4. **Criação de coluna condicional – Risco de Demissão**
   - Nova coluna: `RiscoDemissao`
   - Regra utilizada:
     - Se `JobSatisfaction < 3` → **"ALTO"**
     - Caso contrário → **"BAIXO"**
   - Implementada via **Adicionar Coluna → Coluna Condicional** no Power Query.

> Versão 1: a lógica usa apenas satisfação no trabalho para simplificar o aprendizado. Em versões futuras, será refinada para considerar também salário e outros fatores.

## 🧾 Resultado

Após o ETL, a base passa a ter:
- Coluna `RiscoDemissao` indicando se o funcionário está em **ALTO** ou **BAIXO** risco de demissão.
- Registros sem salário válido removidos.
- Departamentos com nomes padronizados, facilitando análises e criação de dashboards.

## 🛠️ Ferramentas Utilizadas

- **Power BI Desktop**
- **Power Query Editor** (transformações e coluna condicional)
- **GitHub** para versionamento e publicação do arquivo `.pbix`

## 🚀 Próximos Passos

- Refinar a lógica de risco incluindo:
  - Nível de satisfação **e** faixa salarial.
- Criar um **dashboard de RH** com:
  - Visão geral de funcionários em alto risco.
  - Filtros por departamento, cargo e faixa etária.
- Documentar as principais métricas e insights em um novo projeto de portfólio.

## 📁 Como visualizar o arquivo

1. Baixe o arquivo `HR_ETL.pbix` deste repositório.
2. Abra com **Power BI Desktop** (versão gratuita).
3. Acesse o **Power Query Editor** para ver todos os passos de transformação (Applied Steps).
