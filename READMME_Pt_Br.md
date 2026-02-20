# 📊 Análise de Dados de Clientes – Estratégia de Tratamento de Valores Ausentes

## 📌 Visão Geral

Este projeto apresenta uma análise exploratória de dados (EDA) e um fluxo de pré-processamento aplicado a um conjunto de dados com 164 observações.

Um dos principais desafios foi o tratamento de valores ausentes na variável **Age (Idade)**, que possuía aproximadamente 20% de dados faltantes. A solução adotada buscou preservar a coerência estatística e evitar distorções na distribuição.

O notebook demonstra raciocínio estruturado na limpeza, visualização e preparação dos dados para modelagem.

---

## 🎯 Objetivos

- Realizar análise exploratória de dados (EDA)
- Identificar e analisar valores ausentes
- Aplicar estratégias estatisticamente coerentes de imputação
- Preservar a consistência da distribuição
- Preparar o dataset para modelagem

---

## 📂 Resumo do Dataset

- **Total de registros:** 164  
- **Valores ausentes em Age:** 34 (~20%)  
- **Principais variáveis:**
  - Age (Idade)
  - Marital Status (Estado Civil)
  - (Outras variáveis relevantes)

---

## ⚠️ Principal Desafio: Valores Ausentes em Age

A imputação simples pela mediana gerou picos artificiais na distribuição, distorcendo as análises gráficas.

Para resolver o problema, foi aplicada **imputação pela média segmentada por Estado Civil**, utilizando:

```python
df['Age'] = df.groupby('Marital Status')['Age'] \
              .transform(lambda x: x.fillna(x.mean()))
```

### ✅ Por que essa abordagem?

- Preserva a relação entre Idade e Estado Civil
- Evita concentração artificial de valores
- Reduz viés estatístico
- Mantém maior coerência nas visualizações e análises futuras

---

## 📊 Análise Exploratória

O projeto inclui:

- Análise de distribuição
- Visualização da relação entre Idade e Estado Civil
- Diagnóstico de valores ausentes
- Validação após imputação

---

## 🛠️ Tecnologias Utilizadas

- Python 3
- Pandas
- NumPy
- Matplotlib
- Plotly
- Scikit-learn

---

## 🚀 Como Executar

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

Execute o notebook:

```bash
jupyter notebook
```

---

## 📈 Principais Aprendizados

- O tratamento de dados ausentes exige raciocínio estatístico, não apenas correções técnicas.
- A imputação segmentada pode preservar melhor padrões estruturais do que métricas globais.
- Decisões no pré-processamento impactam diretamente a confiabilidade do modelo.

---

## 📌 Possíveis Melhorias Futuras

- Imputação preditiva (ex: regressão)
- Engenharia de atributos
- Treinamento e validação de modelos
- Ampliação do dataset

---

## 👤 Autor

Davi Rodrigues Trindade
Estudante de Ciência de Dados  
LinkedIn: [https://www.linkedin.com/in/davirodriguestrindade/]
