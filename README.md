# TelecomX1_BR - Análise de Churn em Telecomunicações

## 📋 Descrição do Projeto
Este projeto realiza uma análise completa de dados de churn (evasão de clientes) de uma empresa de telecomunicações. O notebook contém um pipeline ETL (Extração, Transformação e Carga) completo com análises visuais para identificar padrões e fatores que influenciam o cancelamento de serviços.

## 🗂️ Estrutura do Projeto

### 1. 📌 Extração
- **Fonte de dados**: API JSON hospedada no GitHub
- **Bibliotecas utilizadas**: 
  - `requests` para acesso à API
  - `pandas` para manipulação de dados
  - `json` para processamento JSON
  - `matplotlib`, `numpy`, `seaborn`, `plotly` para visualizações

### 2. 🔧 Transformação
- **Análise de valores categóricos**: Identificação e contagem de valores únicos em todas as colunas categóricas
- **Tratamento de valores ausentes**: Verificação de nulos em todas as subcategorias de dados
- **Transformação de dados**: 
  - Conversão de `SeniorCitizen` (0/1) para valores categóricos ("No"/"Yes")
  - Verificação de duplicatas em todos os subconjuntos de dados
  - Cálculo de métricas financeiras diárias (`Contas_Diarias`)

### 3. 📊 Carga e Análise
- **Análise de Churn por Contrato**: Estatísticas detalhadas sobre como diferentes tipos de contrato afetam as taxas de evasão
- **Visualizações**:
  - Taxa de evasão por tipo de contrato (gráfico de barras)
  - Distribuição geral de churn (gráfico de barras com porcentagens)
  - Cancelamento por método de pagamento (gráfico de barras agrupadas)

## 🔍 Principais Descobertas

### Análise de Churn por Tipo de Contrato
- **Contrato Month-to-month**: 
  - 55.1% da base de clientes
  - Taxa de evasão: 41.3%
  - Representa 88.6% do churn total
  - Ticket médio: $66.34

- **Contrato One Year**:
  - 20.9% da base de clientes
  - Taxa de evasão: 10.9%
  - Representa 8.9% do churn total

- **Contrato Two Year**:
  - 24.0% da base de clientes
  - Taxa de evasão: 2.8%
  - Representa apenas 2.6% do churn total

### Distribuição Geral de Churn
- Base total: 7.267 clientes
- Clientes que evadiram: 1.869 (25.7%)
- Clientes que permaneceram: 5.174 (73.5%)

## 🛠️ Funcionalidades Implementadas

1. **Função `analise_categorias`**: Analisa automaticamente todas as colunas categóricas do dataset
2. **Função `calcular_contas_diarias`**: Calcula métricas financeiras diárias com tratamento de valores nulos
3. **Função `plot_churn_distribution`**: Gráfico interativo da distribuição de churn
4. **Função `plot_churn_payment`**: Visualização de cancelamentos por método de pagamento

### Visualização de Cancelamento por Método de Pagamento
A função `plot_churn_payment` cria um gráfico de barras agrupadas que mostra a distribuição de churn por método de pagamento. A visualização utiliza:
- Barras coloridas (vermelho para "Sim" e verde para "Não" no churn)
- Texto automático mostrando as contagens
- Layout personalizado com fundo branco e linhas de grade
- Títulos e rótulos em português para melhor compreensão

## 📈 Visualizações

O projeto inclui visualizações interativas usando:
- **Matplotlib/Seaborn**: Para gráficos estáticos
- **Plotly Express**: Para gráficos interativos e detalhados (como o gráfico de cancelamento por método de pagamento)

## 💡 Insights para Ação

1. **Clientes com contrato mensal** representam o maior risco de churn e devem ser alvo de programas de retenção
2. **Contratos de longo prazo** (2 anos) mostram significativamente menor taxa de evasão
3. **Métodos de pagamento** específicos estão associados a maiores taxas de cancelamento

## 🚀 Como Executar

1. Instale as dependências: `pip install requests pandas matplotlib numpy seaborn plotly`
2. Execute o notebook célula por célula
3. As visualizações serão exibidas inline (no Jupyter/Colab) ou em navegador separado

---

## **Análise de Dados TelecomX: Retenção de Clientes**

### **Objetivo do Estudo**
Este projeto tem como finalidade examinar a base de dados da TelecomX, identificando padrões e tendências relacionados à rotatividade de clientes (churn). O churn representa a taxa de cancelamento de serviços, um indicador crítico para avaliar a saúde do negócio e a eficácia das estratégias de retenção.

### **Preparação dos Dados**
Antes das análises, realizamos um rigoroso processo de preparação dos dados seguindo as etapas de ETL (Extração, Transformação e Carregamento):

1. **Importação**: Os dados foram carregados no Google Colab, nossa plataforma de análise.
2. **Limpeza**: Foram tratados valores ausentes, duplicatas e estruturas aninhadas.
3. **Padronização**:
   - Tradução de termos para português
   - Conversão de tipos de dados (object para float/int)
4. **Organização**: Dados estruturados para facilitar análises estatísticas e visualizações.

### **Análise Exploratória (EDA)**

#### **Métricas Principais**
- **Duração média dos contratos**: 32.4 meses
- **Faturamento total**: R$ 64.761,00
- **Receita de serviços adicionais**: R$ 2.283,30
- **Média diária por cliente**: R$ 2,16

#### **Principais Descobertas**
1. **Perfil de Contratos**:
   - A maioria dos clientes mantém contratos por aproximadamente 32 meses
   - Contratos de longo prazo apresentam menor taxa de cancelamento

2. **Comportamento Financeiro**:
   - O faturamento médio diário por cliente é de R$ 2,16
   - Serviços adicionais representam 3,5% da receita total

3. **Padrões de Cancelamento**:
   - Clientes com menos de 12 meses de contrato têm maior propensão ao cancelamento
   - O período crítico para retenção ocorre nos primeiros 6 meses

### **Próximos Passos**
1. **Análise Segmentada**:
   - Comparar comportamento por região e faixa etária
   - Identificar padrões de uso antes do cancelamento

2. **Recomendações Estratégicas**:
   - Desenvolver programas de fidelização para clientes novos
   - Criar alertas para identificar riscos de cancelamento

3. **Modelagem Preditiva**:
   - Implementar modelo para prever probabilidade de churn
   - Estabelecer sistema de scoring de risco

Esta análise preliminar já revela oportunidades importantes para melhorar a retenção de clientes e otimizar as estratégias comerciais da TelecomX.

Este projeto demonstra um fluxo completo de análise de dados para identificar fatores críticos que influenciam a evasão de clientes em uma empresa de telecomunicações.
