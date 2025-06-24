
# 🔍 Projeto 7: Sistema de Recomendação com PySpark 

Este projeto implementa um sistema de recomendação para uma plataforma de **streaming de filmes e séries** utilizando o algoritmo **Alternating Least Squares (ALS)** com **Apache Spark** (via **PySpark**), focado em oferecer recomendações personalizadas a partir de dados de avaliação de usuários.

## 📌 Objetivo

Desenvolver um sistema de recomendação escalável utilizando **PySpark**, baseado no algoritmo **ALS (Alternating  Least Squares)**, com capacidade de prever a afinidade entre usuários e itens. O projeto inclui uma interface web interativa para testes e demonstrações, construída com a biblioteca **Gradio**.

---

## 🚀 Tecnologias Utilizadas

- `PySpark`
- `ALS (Alternating Least Squares)`
- `Gradio` (interface web)
- `Pandas`
- `Matplotlib`
- `Google Colab / SparkSession`

---

## 🛠️ Etapas do Projeto

### 1. 📦 Importação e Configuração Inicial
- Configuração da SparkSession
- Carregamento de bibliotecas essenciais

### 2. 🧼 Pré-processamento dos Dados
- Leitura do dataset de avaliações (usuário, item, nota)
- Conversão para `Spark DataFrame`
- 
### 3. 🤖 Treinamento do Modelo ALS e Resultados 🔍

- **Algoritmo utilizado:** ALS (Alternating Least Squares)
- **Número de observações:** ~100.000 registros
- **Divisão treino/teste:** 80% / 20%
- **Melhores hiperparâmetros encontrados via Cross-Validation:**
  - Rank: 40
  - MaxIter: 10
  - RegParam: 0.05
- **Erro médio (RMSE) no conjunto de teste:** 3.61

🔧 📈 O modelo obteve um RMSE de 3.61, considerando uma escala de avaliações de 1 a 10.  
Esse erro indica uma performance intermediária, com espaço para algumas melhorias.  
Mesmo sem usar informações adicionais sobre usuários e itens, o ALS conseguiu capturar padrões relevantes de recomendação.


### 4. 🎯 Geração de Recomendações
- Uso do método `.transform()` para aplicar o modelo em novos dados
- Ordenação das previsões por pontuação de afinidade (`prediction`)
- **Afinity Score** agrupado pelo ID para retornar a propensão do cliente à compra de determinado item por pontuação de afinidade


### 5. 🌐 Interface Interativa
- Criação de função `fazer_recomendacao(user_id)` para prever os itens mais prováveis de agradar
- Implementação de interface `Gradio`
- Input: ID do usuário
- Output: Top-N recomendações personalizadas

---


## 🎥 Demonstração

A aplicação interativa permite inserir o ID de um usuário e obter uma lista de recomendações personalizadas e em tempo real.
![image](https://github.com/user-attachments/assets/79c11bfe-9e81-4c35-9492-eaba42436676)


---

## 🧠 Próximos Passos

- Adicionar filtros de conteúdo baseado em categorias
- Integração com banco de dados real (ex: PostgreSQL, MongoDB)
