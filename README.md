
# <Previsão de evasão estudantil>

## Desenvolvedores
 - [Geraldo Mendes](https://github.com/Geraldomendes)

---

## Descrição do projeto
Dados os obstáculos enfrentados pelo sistema educacional, a evasão escolar
desempenha um papel crucial, afetando estudantes de diferentes contextos
socioeconômicos. Com base nisso, este trabalho propõe **construir um modelo
preditivo baseado em técnicas de Ciência de Dados para prever a taxa de evasão no
ensino médio e técnico brasileiro**. O estudo aborda a complexidade deste fenômeno,
destacando a sua natureza social e a necessidade de soluções proativas. A
abordagem utiliza dados do censo escolar da educação básica e inclui a análise
exploratória de dados e técnicas de aprendizado de máquina. O modelo proposto visa
prever a evasão escolar, permitindo uma intervenção personalizada e prestando
apoio específico aos alunos desfavorecidos. Além de contribuir para a compreensão
dos fatores associados à evasão escolar, os resultados pretendem oferecer uma
abordagem inovadora para a prevenção desse fenômeno, indo além do meio
acadêmico de modo a proporcionar contribuições práticas ao campo educacional.

--- 

## Estratégia de Solução

**1. Data cleaning:** - Realizar uma limpeza dos dados para remover valores duplicados, inconsistentes, ausentes e remover atributos sem valor significativo para o trabalho.

**2. Análise exploratória:** - Realizar uma análise exploratória para obter insights e entender os fatores causadores da evasão.

**3. Engenharia de atributos**: Aplicar engenharia de atributos baseado nas variáveis originais para melhor descrever o fenônemo que será modelado.

**4. Data preparation**: - Preparar os dados com métodos de normalização/padronização, além de codificar variáveis categóricas para melhorar os resultados.

**5. Machine Learning and Fine Tuning**: Treinar os algoritmos de machine learning e realizar um ajuste de parâmetros para obter um modelo com maior precisão.

**6. Avaliar os resultados de acordo com o problema que está sendo modelado**: Avaliar os resultados dos modelos com base no problema da evasão estudantil .

---

## Performance dos modelos

### Modelo para os cursos técnicos - Decision Tree

Para os cursos técnicos, foram utilizados os algoritmos: Logistic Regression (Regressão Logística), K-Nearest Neighbors e Decision Tree. 

As estatísticas dos modelos após a validação cruzada e ajuste de parâmetros encontram-se na Tabela abaixo:

| **Modelo**          | **Accuracy** | **F1**       | **Precision** | **Recall**    |
|---------------------|--------------|--------------|---------------|---------------|
| Decision Tree       | 0.86 +- 0.03 | 0.76 +- 0.07 | 0.88 +- 0.12  | 0..69 +- 0.15 |
| KNN                 | 0.71 +- 0.06 | 0.48 +- 0.07 | 0.59 +- 0.15  | 0.42 +- 0.06  |
| Logistic Regression | 0.84 +- 0.02 | 0.70 +- 0.09 | 0.87 +- 0.08  | 0.62 +- 0.17  |

O melhor modelo (Decision Tree) foi escolhido com base nas métricas de Precision e Recall, uma vez que:

> **Recall:**
-  No problema da evasão estudantil, o foco principal é identificar todos os alunos em risco, que significa maximizar o recall, uma vez que essa métrica nos dá a probabilidade de uma classe positiva ser corretamente classificada. O recall do modelo no conjunto de teste foi de 69%, foi o maior que conseguimos comparado aos outros, onde 69% dos evadidos foram corretamente identificados.

> **Precisão:**
- Essa também é uma métrica importante se quisermos priorizar alarmes falsos, que seriam os casos de falsos positivos - quando o aluno não é evadido, mas o modelo classifica como tal. O modelo apresentou uma precisão de 88%, ou seja, de todos os alunos que ele classificou como evadido, ele esteve correto em 88% das vezes. Isso garante que esforços de intervenção não sejam desperdiçados em alunos que não estejam em risco.

### Modelo para o nível médio - Random Forest

Para o nível médio, foram utilizados os algoritmos: Logistic Regression (Regressão Logística), K-Nearest Neighbors e Random Forest. 

As estatísticas dos modelos após a validação cruzada e ajuste de parâmetros encontram-se na Tabela abaixo:
| **Modelo**          | **Accuracy** | **Precision** | **Recall**   |
|---------------------|--------------|---------------|--------------|
| KNN                 | 0.87 +- 0.02 | 0.71 +- 0.06  | 0.74 +- 0.03 |
| Random Forest       | 0.97 +- 0.00 | 0.95 +- 0.00  | 0.89 +- 0.01 |
| Logistic Regression | 0.87 +- 0.02 | 0.68 +- 0.03  | 0.80 +- 0.02 |

O melhor modelo (Random Forest) foi escolhido com base nas métricas de Precision e Recall, uma vez que:

> **Recall:**
-  No problema da evasão estudantil, o foco principal é identificar todos os alunos em risco, que significa maximizar o recall, uma vez que essa métrica nos dá a probabilidade de uma classe positiva ser corretamente classificada. O recall do modelo no conjunto de teste foi de 89%, garantindo que poucos alunos evadidos fossem deixados de fora, isto é,89% dos evadidos foram corretamente classificados pelo modelo.

> **Precisão:**
- Essa também é uma métrica importante se quisermos priorizar alarmes falsos, que seriam os casos de falsos positivos - quando o aluno não é evadido, mas o modelo classifica como tal. O modelo apresentou uma precisão de 95%, ou seja, de todos os alunos que ele classificou como evadido, ele esteve correto em 95% das vezes. Isso garante que esforços de intervenção não sejam desperdiçados em alunos que não estejam em risco.

---
## Conclusões

... 

### Organização de diretórios


```
.
├── data/              # Diretório contendo todos os arquivos de dados
│   ├── external/      # Arquivos de dados de fontes externas
│   ├── processed/     # Arquivos de dados processados
│   └── raw/           # Arquivos de dados originais, imutáveis
├── models/            # Modelos treinados e serializados, predições ou resumos de modelos
├── notebooks/         # Diretório contendo todos os notebooks utilizados nos passos
└── README.md          # Informações gerais do projeto

```


