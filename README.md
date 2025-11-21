# 🛡️ Previsão de Qualidade de Veículos para Precificação de Risco (Random Forest)

## 💡 Visão Geral do Projeto

Este projeto utiliza o Machine Learning para resolver um problema crítico de **Vendas e Risco**: prever a **Qualidade e o Risco de Manutenção** de veículos. O objetivo final é criar um sistema que categorize veículos em **Baixo, Médio ou Alto Risco**, permitindo que o serviço de assistência 24 horas seja precificado de forma justa e lucrativa.

O modelo **Random Forest** foi escolhido por sua alta precisão em classificação e sua capacidade de fornecer a **Importância das Features** (Explicabilidade), fundamental para justificar a precificação.

---
### ⚙️ Metodologia e Modelagem

| Fase | Detalhes | Foco |
| :--- | :--- | :--- |
| **Algoritmo** | **Random Forest Classifier** | Classificação de risco em múltiplas categorias. |
| **Métricas** | **Classification Report** (Precisão, Recall, F1-Score) | Avaliação da performance do modelo em cada classe de risco. |
| **Explicabilidade (XAI)** | **Feature Importance** | Identificar quais características do carro mais influenciam o custo de assistência. |

---
### ✅ Resultados e Análise de Risco

O modelo treinado atingiu uma **acurácia de 100%** no conjunto de dados, demonstrando forte capacidade de separar as classes de risco.

#### 1. Importância dos Fatores de Risco

A análise de importância das *features* estabeleceu a hierarquia para a tomada de decisão de preço:

| Fator | Importância | Relevância para Precificação |
| :--- | :---: | :--- |
| **Exigencia\_Manutencao** | **50.47%** | **Fator Dominante.** Deve ser o principal driver do preço. |
| **Segurança (0-10)** | **33.33%** | **Forte Contrapeso.** Usado para oferecer descontos (se alta) ou aumentar o preço (se baixa). |
| **Porta\_Malas (L)** | 14.20% | Influência Moderada. |
| **Portas** | 2.00% | Influência Marginal. |

#### 2. Previsão para o Novo Veículo (Exemplo)

O modelo foi usado para classificar um novo veículo com **Exigência de Manutenção Média** e **Segurança 8**.

| Previsão Final | Probabilidade de Risco | Diretriz de Negócio |
| :--- | :---: | :--- |
| **Risco Médio** | **72%** | Precificar na faixa intermediária de risco. |

**Justificativa:** O risco foi classificado como **Médio** devido ao equilíbrio entre a **Manutenção Média** (puxando para cima) e a **Alta Segurança (8)** (puxando para baixo). O modelo demonstra que a alta segurança atenuou o risco, impedindo a classificação como 'Alto'.

---
## 🎯 Conclusão

Este projeto demonstra a aplicação de Machine Learning para a criação de um **sistema de precificação de risco baseado em dados**. O modelo **Random Forest** fornece à área de vendas as ferramentas para:

1.  **Otimizar Receita:** Ajustar o preço do serviço de assistência diretamente ao risco real de manutenção.
2.  **Transparência:** Justificar o preço ao cliente com base em fatores objetivos (Exigência de Manutenção e Segurança).
