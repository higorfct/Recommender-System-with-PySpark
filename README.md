
# 🔍 Projeto 6: Sistema de Recomendação com PySpark 

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

### 2. 📊 Análise Exploratória
![image](https://github.com/user-attachments/assets/a20c3c2e-d198-46ec-b49c-45b5d8fc6a73)

**Interpretação do Gráfico 1**: A distribuição das avaliações (ratings) mostra que, embora avaliações positivas sejam predominantes, ainda existe uma quantidade considerável de avaliações de nota baixa, sugerindo que ainda existem alguns gargalos que podem ser enfrentados e corrigidos para melhorar a experiência dos usuários com os produtos.

![image](https://github.com/user-attachments/assets/84ddff1e-0304-47b0-a046-10e5a95b74f7)

**Interpretação do Gráfico 2**: O Gráfico 2 sugere que a maioria das avaliações concentra-se em um único usuário (usuário 1005), podendo ser fonte de viés nas análises caso suas avaliações não sejam representativas do comportamento médio dos demais usuários. Por outro lado, a baixa participação dos demais usuários sugere uma oportunidade de estimular mais o engajamento na plataforma visando melhorar a qualidade dos dados, o aprimoramento dos sistemas de recomendação, a identificação de oportunidades de melhoria e o fortalecimento da confiança na plataforma, gerando, assim maior valor para o negócio.


![image](https://github.com/user-attachments/assets/2fbff6f5-c1e5-40aa-ac9d-f47516485786)

**Interpretação do Gráfico 3**: O Gráfico 3 revela uma distribuição desigual no número de avaliações por item: enquanto poucos itens concentram a maior parte das interações (como os itens 9001 a 9004, com 5 a 6 avaliações cada), a maioria dos demais itens recebeu de 1 a 3 avaliações. Essa assimetria indica uma concentração de atenção em um pequeno conjunto de produtos, enquanto grande parte do catálogo permanece subavaliada. Esse padrão pode comprometer a qualidade das recomendações, reforçando o viés de popularidade e limitando a diversidade de sugestões. Promover a avaliação de itens pouco explorados é uma estratégia valiosa para enriquecer a base de dados, melhorar a representatividade do sistema de recomendação e ampliar o alcance do conteúdo oferecido.



**Conclusão da Análise Exploratória**: A análise exploratória mostrou claramente que os dados são esparsos, que é o esperado quando se trata de sistemas de recomendação. Sendo assim, isso reforça a necessidade de utilizar o algorítmo **ALS (Alternating Least Squares)** devido sua capacidade de lidar com esse tipo de dados.





### 3. 🧼 Pré-processamento dos Dados
- Leitura do dataset de avaliações (usuário, item, nota)
- Conversão para `Spark DataFrame`
- 
### 4. 🤖 Treinamento do Modelo ALS
- Treinamento do modelo com `ALS` do `pyspark.ml.recommendation`
- Ajuste de parâmetros como `rank`, `maxIter`, `regParam`
- **Afinity Score** agrupado pelo ID para retornar a propensão do cliente à compra de determinado item 

### 5. 🎯 Geração de Recomendações
- Uso do método `.transform()` para aplicar o modelo em novos dados
- Ordenação das previsões por pontuação de afinidade (`prediction`)
- **Afinity Score** agrupado pelo ID para retornar a propensão do cliente à compra de determinado item por pontuação de afinidade


### 6. 🌐 Interface Interativa
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
