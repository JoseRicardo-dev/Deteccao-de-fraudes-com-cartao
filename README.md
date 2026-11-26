# 💳 Detecção de Fraudes em Cartões de Crédito com Machine Learning

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Machine%20Learning-FF6F00?style=for-the-badge" />
</p>

## 📌 Sobre o projeto

A detecção de fraudes em cartões de crédito é um dos principais desafios enfrentados pelas instituições financeiras. Com o crescimento das transações digitais, identificar operações fraudulentas de maneira rápida e precisa tornou-se essencial para reduzir prejuízos e aumentar a segurança financeira.

Este projeto tem como objetivo desenvolver um modelo de Machine Learning capaz de identificar transações potencialmente fraudulentas, utilizando técnicas de análise de dados, balanceamento de classes e classificação supervisionada.

Para isso, foi desenvolvido um modelo de **Random Forest**, utilizando a técnica **SMOTE (Synthetic Minority Over-sampling Technique)** para lidar com o desbalanceamento entre transações legítimas e fraudulentas.

O projeto foi desenvolvido em Python, utilizando bibliotecas de Ciência de Dados e Machine Learning.

## 🎯 Objetivos

- Explorar e compreender os dados de transações financeiras.
- Identificar o desbalanceamento entre transações legítimas e fraudulentas.
- Realizar análise exploratória de dados (EDA).
- Investigar valores ausentes e características estatísticas.
- Aplicar técnicas de balanceamento utilizando SMOTE.
- Treinar um modelo de classificação Random Forest.
- Avaliar o desempenho do modelo por meio de métricas de classificação.

## 🛠️ Tecnologias e bibliotecas

| Tecnologia | Aplicação |
|---|---|
| Python | Linguagem principal |
| Pandas | Manipulação e análise de dados |
| NumPy | Operações numéricas |
| Matplotlib | Visualização de dados |
| Seaborn | Análise gráfica |
| Scikit-learn | Divisão dos dados, treinamento e avaliação |
| Imbalanced-learn | Balanceamento de classes com SMOTE |
| Jupyter Notebook | Desenvolvimento e documentação |

## 📂 Estrutura do projeto

```text
Deteccao-de-fraudes-com-cartao/
│
├── Detecção_de_fraude.ipynb
│
└── README.md
```

## 🔍 Etapas do desenvolvimento

### 1. Importação e exploração dos dados

Inicialmente, foram utilizadas as bibliotecas Pandas, NumPy, Matplotlib e Seaborn para carregar, visualizar e explorar o conjunto de dados.

Foram realizadas análises para compreender:
- Estrutura e tipos das variáveis.
- Distribuição das informações.
- Estatísticas descritivas.
- Existência de valores ausentes.

### 2. Análise do desbalanceamento

Um dos principais desafios na detecção de fraudes é o desbalanceamento das classes.

Isso acontece porque transações fraudulentas representam uma parcela muito pequena do total de operações financeiras.

Foi utilizada a biblioteca Seaborn para visualizar a distribuição das classes, sendo:

- **Classe 0:** Transações legítimas.
- **Classe 1:** Transações fraudulentas.

### 3. Preparação dos dados

Foi realizada a separação entre as variáveis independentes (X) e a variável alvo (y).

Em seguida, os dados foram divididos em conjuntos de treinamento e teste, utilizando:

- 80% para treinamento.
- 20% para teste.
- `random_state=42` para reprodutibilidade.
- `stratify=y` para preservar a proporção das classes.

### 4. Balanceamento utilizando SMOTE

Para reduzir o impacto do desbalanceamento, foi aplicada a técnica SMOTE.

O SMOTE cria exemplos sintéticos da classe minoritária, ajudando o modelo a aprender melhor os padrões associados às transações fraudulentas.

**Importante:** O balanceamento foi aplicado somente aos dados de treinamento, preservando o conjunto de teste para uma avaliação mais realista.

### 5. Treinamento do modelo Random Forest

Foi utilizado o algoritmo Random Forest Classifier, com os seguintes parâmetros:

```python
RandomForestClassifier(
    n_estimators=100,
    random_state=42
)
```

O modelo foi treinado utilizando os dados de treinamento após a aplicação do SMOTE.

Posteriormente, foram realizadas previsões sobre os dados de teste.

### 6. Avaliação do modelo

Para avaliar o desempenho, foram utilizadas:

- **Precision:** Proporção de previsões positivas que realmente são fraudes.
- **Recall:** Proporção de fraudes reais identificadas pelo modelo.
- **F1-Score:** Média harmônica entre Precision e Recall.
- **Matriz de Confusão:** Permite visualizar os acertos e erros da classificação.

## 📊 Resultados obtidos

O modelo Random Forest apresentou resultados promissores na identificação de transações fraudulentas.

Com base na execução documentada no notebook, a matriz de confusão foi:

```text
                 Previsão
              Normal  Fraude

Real Normal     1985      0
Real Fraude        1      7
```

### Desempenho na identificação de fraudes

| Métrica | Resultado |
|---|---:|
| Precision | 100% |
| Recall | 87,5% |
| F1-Score | 93,3% |
| Acurácia | 99,95% |

<details>
<summary><strong>📌 Entenda os resultados</strong></summary>

- **1.985 verdadeiros negativos:** transações legítimas classificadas corretamente.
- **0 falsos positivos:** nenhuma transação legítima foi classificada incorretamente como fraude.
- **1 falso negativo:** uma fraude não foi identificada pelo modelo.
- **7 verdadeiros positivos:** sete transações fraudulentas foram identificadas corretamente.

O Recall de 87,5% demonstra que o modelo conseguiu identificar 7 das 8 fraudes presentes no conjunto de teste.

A Precision de 100% indica que todas as transações classificadas como fraudulentas eram efetivamente fraudes nesse conjunto de teste.

</details>

## 💡 Principais aprendizados

Durante o desenvolvimento deste projeto, foram explorados conceitos importantes de Ciência de Dados e Machine Learning:

- Análise exploratória de dados.
- Identificação e tratamento de valores ausentes.
- Preparação de variáveis para Machine Learning.
- Separação estratificada de dados.
- Tratamento de conjuntos desbalanceados.
- Aplicação da técnica SMOTE.
- Treinamento de modelos de classificação.
- Avaliação utilizando métricas de desempenho.

## 🚀 Possíveis melhorias futuras

Como evolução do projeto, algumas melhorias podem ser exploradas:

- Comparar Random Forest com Logistic Regression, Decision Tree e XGBoost.
- Otimizar os hiperparâmetros do modelo.
- Avaliar o desempenho utilizando validação cruzada estratificada.
- Investigar diferentes estratégias de balanceamento.
- Analisar a curva Precision-Recall.
- Ajustar o threshold de classificação para reduzir falsos negativos.
- Desenvolver uma interface interativa para simular a identificação de fraudes.

## ▶️ Como executar o projeto

**1. Clone o repositório:**

```bash
git clone https://github.com/JoseRicardo-dev/Deteccao-de-fraudes-com-cartao.git
```

**2. Acesse a pasta:**

```bash
cd Deteccao-de-fraudes-com-cartao
```

**3. Instale as dependências:**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
```

**4. Disponibilize o arquivo `creditcard.csv` no ambiente.**

O notebook utiliza o seguinte caminho:

```python
df = pd.read_csv('/content/creditcard.csv')
```

Ajuste esse caminho conforme o local em que o arquivo estiver armazenado.

**5. Execute o Jupyter Notebook:**

```bash
jupyter notebook
```

Abra o arquivo `Detecção_de_fraude.ipynb` e execute as células.

## 👨‍💻 Autor

**José Ricardo**

Estudante e entusiasta de Ciência de Dados, com interesse em análise de dados, Machine Learning e desenvolvimento de soluções orientadas por dados.

🔗 **GitHub:** [JoseRicardo-dev](https://github.com/JoseRicardo-dev)

---

⭐ Se você gostou deste projeto, considere deixar uma estrela no repositório!

**Feedbacks, sugestões e contribuições são muito bem-vindos.**
