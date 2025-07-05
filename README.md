# projeto-inadimplencia
MVP Sprint: Análise de Dados e Boas Práticas

# 🧠 Previsão de Inadimplência com Dados Quantitativos

Este projeto tem como objetivo analisar um conjunto de dados financeiros e comportamentais de clientes de uma instituição de crédito, a fim de prever a **probabilidade de inadimplência** e auxiliar na tomada de decisões mais assertivas sobre concessão de crédito.

---

## 📂 Sobre o Dataset

- **Origem**: Base hipotética.
- **Formato**: CSV delimitado por ponto e vírgula (`;`)
- **Registros**: 10.986 clientes
- **Variável-alvo**: `Resposta` (0 = adimplente, 1 = inadimplente)

### 🧾 Variáveis disponíveis

| Coluna         | Descrição |
|----------------|-----------|
| `cliente`      | Identificador único do cliente |
| `Resposta`     | Status de pagamento do cliente |
| `RegRisc`      | Região de risco (I, II, III, IV) |
| `Atrasos`      | Número de dias de atraso nos pagamentos |
| `TempoRel`     | Tempo de relacionamento com a instituição (em dias) |
| `valorFatura`  | Valor médio da fatura mensal |
| `GastosAlim`   | Percentual de gastos com alimentação |
| `RendaMensal`  | Renda mensal do cliente |

---

## 🧩 Hipóteses levantadas

1. Clientes com maior número de atrasos têm maior chance de inadimplência ✅  
2. Regiões de risco mais altas (III e IV) estão associadas a maior inadimplência ❌  
3. Menor tempo de relacionamento indica maior risco de inadimplência ✅  
4. Existe correlação entre valor da fatura e renda mensal ❌  
5. Gastos com alimentação indicam menor capacidade de pagamento ❌  

---

## ⚙️ Etapas Realizadas

### 1. 📊 Análise Exploratória de Dados (EDA)
- Verificação de tipos de dados e dados ausentes
- Histogramas e boxplots para entender distribuição e outliers
- Estatísticas descritivas (média, desvio padrão)
- Matriz de correlação
- Comparações entre grupos (adimplentes vs inadimplentes)

### 2. 🧼 Pré-Processamento
- Conversão da variável `cliente` para string
- Codificação da variável `RegRisc` com **One-Hot Encoding**
- Normalização com `MinMaxScaler`
- Padronização com `StandardScaler`
- Separação em conjunto de treino e teste com `train_test_split`

---

## 🧪 Ferramentas e Bibliotecas

- Python (pandas, numpy)
- Visualização: seaborn, matplotlib
- Pré-processamento e modelagem: `scikit-learn`

---

## 📉 Principais Insights

- **Atrasos**: Boa preditora de inadimplência (correlação ≈ 0.38)
- **Tempo de relacionamento**: Clientes com histórico mais longo tendem a ser mais confiáveis
- **Regiões de Risco**: Regiões I e II apresentaram maior inadimplência (hipótese contrariada)
- **Gastos com alimentação**: Maior percentual de gastos se correlaciona com **maior** capacidade de pagamento

---

## 📁 Organização dos Arquivos

| Arquivo | Descrição |
|--------|-----------|
| `Inadimplencia_quantitativa_2.csv` | Base de dados original |
| `inadimplencia_analysis.ipynb` | Notebook com toda a análise, visualizações e pré-processamento |
| `README.md` | Descrição geral do projeto |

---

## 📌 Conclusão

Este estudo evidenciou a importância da análise exploratória e do pré-processamento para projetos de ciência de dados. A análise visual e estatística permitiu a validação (ou refutação) de hipóteses iniciais, e a transformação dos dados prepara o terreno para a aplicação de algoritmos de Machine Learning supervisionado para classificação binária.
