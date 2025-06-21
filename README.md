
# 🔍 Sistema de Recomendação com Spark (ALS)

Este projeto implementa um sistema de recomendação utilizando o algoritmo **Alternating Least Squares (ALS)** com **Apache Spark**, focado em oferecer recomendações personalizadas a partir de dados de avaliação de usuários.

## 📌 Objetivo

Desenvolver e testar um sistema de recomendação escalável utilizando PySpark, com capacidade de previsão de afinidade entre usuários e itens, além de fornecer uma interface web simples para testes interativos.

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
- Análise exploratória rápida: distribuição de ratings, quantidade de usuários/itens

### 3. 🤖 Treinamento do Modelo ALS
- Divisão dos dados em treino e teste
- Treinamento do modelo com `ALS` do `pyspark.ml.recommendation`
- Ajuste de parâmetros como `rank`, `maxIter`, `regParam`
- Avaliação com RMSE

### 4. 🎯 Geração de Recomendações
- Criação de função `fazer_recomendacao(user_id)` para prever os itens mais prováveis de agradar
- Uso do método `.transform()` para aplicar o modelo em novos dados
- Ordenação das previsões por pontuação de afinidade (`prediction`)

### 5. 🌐 Interface Interativa
- Implementação de interface `Gradio`
- Input: ID do usuário
- Output: Top-N recomendações personalizadas

---

## 💡 Principais Insights

- O ALS é altamente eficaz para problemas de recomendação baseados em **fatores latentes**, mesmo em bases esparsas.
- A previsão de afinidade é interpretada diretamente pela coluna `prediction`, quanto maior, maior a probabilidade do item ser bem aceito.
- Com `PySpark`, o sistema se mantém escalável mesmo com grandes volumes de dados.
- A integração com `Gradio` permite testes interativos sem necessidade de conhecimento técnico por parte do usuário final.

---

## 🧪 Como Rodar

```bash
# Clonar o repositório
git clone https://github.com/seuusuario/spark-sistema-recomendacao.git
cd spark-sistema-recomendacao

# Subir o ambiente no Colab ou configurar o PySpark localmente

# Rodar o notebook: SPARK_Sistema_de_Recomendacao_v2.ipynb
```

---

## 🎥 Demonstração

A aplicação interativa permite inserir o ID de um usuário e obter recomendações em tempo real.

---

## 📁 Estrutura

```
📦 spark-sistema-recomendacao
 ┣ 📜 SPARK_Sistema_de_Recomendacao_v2.ipynb
 ┗ 📄 README.md
```

---

## 🧠 Próximos Passos

- Realizar ajuste fino de hiperparâmetros com `CrossValidator`
- Adicionar filtros de conteúdo baseado em categorias
- Integração com banco de dados real (ex: PostgreSQL, MongoDB)
