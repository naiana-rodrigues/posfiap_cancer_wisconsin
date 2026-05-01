````md
# Predição de Câncer de Mama com Machine Learning

## Objetivo

Este projeto tem como objetivo analisar o dataset Breast Cancer Wisconsin e comparar modelos de Machine Learning para predição de diagnóstico de câncer de mama (benigno ou maligno).

Foram avaliados:

- Regressão Logística
- Árvore de Decisão
- Regressão Logística com PCA (redução de dimensionalidade)

---

## Base de Dados

Dataset público hospedado no Kaggle:

Breast Cancer Wisconsin Dataset

Fonte:

`uciml/breast-cancer-wisconsin-data`

---

## Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- SHAP
- KaggleHub

---

## Instalação

Clone o repositório:

```bash
git clone <url-do-repositorio>
cd <nome-do-repositorio>
````

Instale dependências:

```bash
pip install -r requirements.txt
```

---

## Bibliotecas Principais

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
shap
kagglehub
```

---

## Estrutura Analítica do Projeto

## 1. Importação da Base

Leitura direta do Kaggle utilizando KaggleHub.

## 2. Tratamento de Dados

* Remoção de coluna vazia (`Unnamed: 32`)
* Conversão do diagnóstico:

| Original | Convertido |
| -------- | ---------- |
| M        | 1          |
| B        | 0          |

## 3. Análise Exploratória

* Estatísticas descritivas
* Correlação geral
* Correlação apenas casos malignos
* Heatmaps

## 4. Modelagem

### Regressão Logística

Modelo binário com padronização via `StandardScaler`.

### Árvore de Decisão

Modelo interpretável com controle de overfitting:

* max_depth=6
* min_samples_leaf=2

### PCA + Regressão Logística

Redução de dimensionalidade para 10 componentes principais (~95% da variância).

---

## Principais Resultados

## Regressão Logística

Excelente performance com poucos erros.

## Árvore de Decisão

Performance inferior, principalmente em falsos negativos.

## PCA + Regressão Logística

Melhor resultado geral.

### Comparação das Matrizes de Confusão

Regressão padrão:

```text
[[71,1],
 [2,40]]
```

Regressão com PCA:

```text
[[72,0],
 [1,41]]
```

### Conclusão

O PCA reduziu erros críticos (falsos negativos) e aumentou a capacidade preditiva.

---

## Interpretabilidade com SHAP

Foram aplicadas análises SHAP para explicar decisões dos modelos.

Principais variáveis relevantes:

* perimeter_worst
* concave points_worst
* texture_mean
* texture_worst
* area_worst
* radius_worst

---

## Considerações Técnicas

* Dataset pequeno para produção real
* Resultados promissores para estudo acadêmico
* PCA mostrou ganho relevante
* Regressão Logística foi o modelo mais estável

---

## Como Executar

Abra notebook no Google Colab ou Jupyter e execute células em ordem.

---

## Possíveis Melhorias Futuras

* Cross Validation
* Random Forest / XGBoost
* Deploy em API REST
* Dashboard com Streamlit
* Base de dados maior

---

## Autor

Projeto acadêmico para estudo de Machine Learning aplicado à saúde.

```
```
