# Formação Power BI Analyst - Desafio de Projeto DIO: Azure Company

Este repositório contém os arquivos desenvolvidos para o Desafio de Projeto da Formação Power BI Analyst da DIO (Digital Innovation One). O projeto envolve a criação de um modelo de banco de dados e a geração de um relatório gerencial utilizando o Power BI.

## Arquivos do Repositório

| Arquivo | Descrição |
| :--- | :--- |
| `BD_azure_company.sql` | Script SQL para a criação do esquema de banco de dados (`azure_company`), definição de tabelas, restrições (chaves primárias, estrangeiras, checagens e unicidade) e inserção dos dados de exemplo. |
| `azure_company.pbix` | Arquivo do relatório gerencial de exemplo (Company Report) desenvolvido no Power BI, representando a visualização dos dados. |

## 1. Banco de Dados (`BD_azure_company.sql`)

O script SQL define um esquema de banco de dados relacional que simula dados de uma empresa. Ele é composto pelas seguintes tabelas:

* **`departament`**: Informações sobre os departamentos.
* **`employee`**: Informações sobre os funcionários.
* **`dept_locations`**: Localizações dos departamentos.
* **`project`**: Informações sobre os projetos.
* **`works_on`**: Relação de horas trabalhadas por funcionário em cada projeto.
* **`dependent`**: Dependentes dos funcionários.

### Diagrama Simplificado do Modelo de Dados

O modelo segue um esquema típico de banco de dados corporativo, com as seguintes relações-chave:

* **`departament`** $\leftrightarrow$ **`employee`** (Um departamento tem muitos funcionários, um funcionário pertence a um departamento).
* **`departament`** $\leftrightarrow$ **`employee`** (Relação de Gerência: um gerente - que é um funcionário - gerencia um departamento).
* **`employee`** $\leftrightarrow$ **`employee`** (Relação de Supervisão: um funcionário é supervisionado por outro funcionário).
* **`departament`** $\leftrightarrow$ **`project`** (Um departamento controla muitos projetos).
* **`employee`** $\leftrightarrow$ **`project`** (Muitos para Muitos via **`works_on`**: Um funcionário trabalha em vários projetos, e um projeto tem vários funcionários).
* **`employee`** $\leftrightarrow$ **`dependent`** (Um funcionário pode ter vários dependentes).

## 2. Relatório Power BI (`image_dee5c4.png`)

A imagem abaixo demonstra o painel criado no Power BI, utilizando os dados inseridos no banco de dados. O relatório é focado em métricas de recursos humanos e projetos.

<img width="1309" height="734" alt="image" src="https://github.com/user-attachments/assets/156148e5-d80b-4fda-a9a5-640c807e5cfd" />


O painel é composto pelos seguintes visuais:

* **Qtd Empregados por Gerente**: Gráfico de colunas mostrando a contagem de funcionários sob a supervisão de cada gerente (identificado pelo seu SSN).
* **Média de Salário por Departamento**: Gráfico de colunas apresentando o salário médio dos funcionários em cada departamento (`Headquarters`, `Research`, `Administration`).
* **Horas Trabalhadas por Projeto**: Gráfico de rosca (donut chart) que exibe a distribuição das horas totais trabalhadas pelos funcionários em cada projeto (e a respectiva porcentagem).

---

Autor: Wesley Calsonari Nogueira
