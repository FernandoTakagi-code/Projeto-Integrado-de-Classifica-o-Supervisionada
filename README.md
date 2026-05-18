# Projeto Integrado de Classificação Supervisionada: O Desastre do Titanic 🚢

Este projeto consiste em uma análise preditiva utilizando algoritmos de Machine Learning supervisionado para classificar a sobrevivência dos passageiros do Titanic. O objetivo principal é comparar o desempenho, o custo computacional e a interpretabilidade de três modelos distintos: **XGBoost, SVM (RBF) e Random Forest**, utilizando o `scikit-learn` e o arquivo de dados fornecido.

---

## 🎯 Objetivo

Aplicar técnicas avançadas de pré-processamento de dados e ajuste de hiperparâmetros para prever a variável alvo `2urvived` (Sobrevivência: 0 = Não, 1 = Sim), avaliando criticamente os resultados obtidos por meio de múltiplas métricas de classificação.

---

## 🧩 Estrutura da Tarefa

### 📂 Dataset Utilizado
Os dados estão contidos no arquivo `train_and_test2.csv`, que unifica informações demográficas e de bilheteria dos passageiros do Titanic.
* **Variável Target:** `2urvived`
* **Principais Features Utilizadas:** `Age`, `Fare`, `Sex`, `Pclass`, `SibSp`, `Parch`, `Embarked`.

### 🛠️ Pré-processamento (Pipeline)
1.  **Tratamento de Dados Ausentes:** Imputação de valores nulos para idade (`Age`) e porto de embarque (`Embarked`).
2.  **Escalonamento:** Aplicação de `StandardScaler` para normalizar as variáveis numéricas (`Age`, `Fare`).
3.  **Codificação de Categóricas:** Transformação de variáveis categóricas (`Sex`, `Embarked`, `Pclass`) utilizando `OneHotEncoder`.

### 🤖 Modelagem e Otimização
O projeto realiza o treinamento de três algoritmos robustos:
* **XGBoost** (Gradient Boosting adaptado para alta performance)
* **Support Vector Machine (SVM)** com kernel RBF
* **Random Forest** (Ensemble de árvores de decisão)

Para encontrar a melhor combinação de parâmetros, foi utilizado o **`RandomizedSearchCV`** integrado com validação cruzada estratificada (**`StratifiedKFold`**), garantindo o balanceamento das classes durante o treino.

---

## 📊 Métricas de Avaliação

A eficácia de cada modelo é medida utilizando:
* **Métrica Principal:** `ROC-AUC` (Área sob a Curva ROC)
* **Métricas Secundárias:** Acurácia, F1-Score e Matriz de Confusão.
* **Visualizações Graficas:** Curvas ROC e Curvas Precision-Recall comparativas.

---

## 🚀 Como Executar o Projeto no Google Colab

1. Acesse o [Google Colab](https://colab.research.google.com/).
2. Crie um novo notebook ou faça o upload do seu script `.ipynb`.
3. Certifique-se de fazer o upload do arquivo de dados no ambiente do Colab:
   * No menu lateral esquerdo, clique no ícone de pasta (**Arquivos**).
   * Clique em **Fazer upload para o armazenamento da sessão** e selecione o arquivo `train_and_test2.csv`.
