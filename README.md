# 🏦 Data Girls Finance - Pipeline ETL de Crédito

## 📋 Sobre o Projeto

Pipeline ETL automatizado para processamento de dados de crédito, desenvolvido como projeto final do **Bootcamp [RE]Start - Trilha Engenharia de Dados**.

O projeto consiste em extrair dados do Kaggle, realizar limpeza e transformação, gerar insights e disponibilizar informações em um dashboard interativo.

---

## 🏗️ Arquitetura do Pipeline
┌─────────────────────────────────────────────────────────────────┐
│ PIPELINE ETL AUTOMATIZADO │
├─────────────────────────────────────────────────────────────────┤
│ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ │
│ │ EXTRACT │───▶│ TRANSFORM │───▶│ LOAD │ │
│ │ │ │ │ │ │ │
│ │ • Kaggle API │ │ • Limpeza │ │ • CSV/JSON │ │
│ │ • CSV │ │ • Validação │ │ • Dashboard │ │
│ │ │ │ • Features │ │ • Power BI │ │
│ └──────────────┘ └──────────────┘ └──────────────┘ │
│ │ │ │ │
│ └────────────────────┴────────────────────┘ │
│ │ │
│ ┌───────▼───────┐ │
│ │ AIRFLOW │ │
│ │ Agendamento │ │
│ │ (Simulado) │ │
│ └───────────────┘ │
└─────────────────────────────────────────────────────────────────┘





## 🛠️ Tecnologias Utilizadas

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| **Python** | 3.14 | Linguagem principal |
| **Pandas** | 2.0.3 | Manipulação de dados |
| **NumPy** | 1.24.3 | Operações numéricas |
| **Kaggle API** | 1.5.16 | Extração de dados |
| **Power BI** | Desktop | Visualização e dashboard |
| **Git/GitHub** | - | Versionamento |



## 📊 Resultados Obtidos

### Estatísticas Finais

| Métrica | Valor |
|---------|-------|
| **Total de clientes** | 11.811 |
| **Colunas no dataset** | 32 |
| **Média de idade** | 34,1 anos |
| **Renda média** | R$ 186.672,22 |

### Distribuição dos Scores

| Score | Quantidade | Percentual |
|-------|------------|------------|
| **Standard** | 6.554 | 55,5% |
| **Poor** | 3.269 | 27,7% |
| **Good** | 1.988 | 16,8% |

### Features Criadas

| Feature | Descrição |
|---------|-----------|
| **Age_Category** | Classificação por idade (Jovem/Adulto/Sênior) |
| **Payment_Risk** | Risco de pagamento (Baixo/Médio/Alto) |
| **Score_Numeric** | Score numérico (1-3) para gráficos |
| **Income_Category** | Faixa de renda (Baixa/Média/Alta) |
| **Credit_Utilization_Ratio** | Taxa de uso do crédito |



## 🚀 Como Executar o Pipeline

### 1. Clonar o repositório

bash
git clone https://github.com/seu-usuario/projeto-credit-score.git
cd projeto-credit-score
2. Instalar dependências
bash
pip install -r requirements.txt
3. Configurar Kaggle API
bash
# Baixe o token em: https://www.kaggle.com/settings
# Coloque em: C:\Users\seu-usuario\.kaggle\kaggle.json
4. Executar o pipeline completo
bash
# Executar todos os scripts em sequência
python scripts/05_pipeline_automatizado.py
5. Executar scripts individuais
bash
# Extração
python scripts/01_baixar_dados.py

# Limpeza e transformação
python scripts/03_limpar_dados.py

# Preparação para dashboard
python scripts/04_upload_nuvem.py
📁 Estrutura do Projeto
text
📁 projeto-credit-score/
│
├── 📁 dados/
│   ├── 📁 raw/                      # Dados brutos
│   │   └── train.csv                # Dataset original (100.000 registros)
│   └── 📁 processed/                # Dados processados
│       ├── dados_prontos.csv        # Dados limpos (11.811 registros)
│       ├── dashboard_score.csv      # Resumo por score
│       ├── dashboard_risco.csv      # Resumo por risco
│       ├── dashboard_idade.csv      # Resumo por idade
│       ├── relatorio_validacao.json # Validações
│       └── resumo_final.json        # Estatísticas finais
│
├── 📁 scripts/                      # Scripts Python
│   ├── 01_baixar_dados.py           # Extração do Kaggle
│   ├── 02_explorar_dados.py         # Análise exploratória
│   ├── 03_limpar_dados.py           # Limpeza e transformação
│   ├── 04_upload_nuvem.py           # Preparação para dashboard
│   └── 05_pipeline_automatizado.py  # Automação (Airflow simulado)
│
├── 📁 dashboard/                    # Dashboard Power BI
│   └── dashboard_credit_score.pbix
│
├── 📁 prints/                       # Evidências do funcionamento
│   ├── 01_extracao.png              # Extração de dados
│   ├── 02_transformacao.png         # Transformação
│   ├── 03_arquivos_gerados.png      # Arquivos processados
│   ├── 04_pipeline_automatizado.png # Pipeline rodando
│   └── 05_dashboard_final.png       # Dashboard final
│
├── 📄 README.md                     # Documentação
├── 📄 requirements.txt              # Dependências
└── 📄 .gitignore                    # Arquivos ignorados
📸 Evidências do Funcionamento
1. Extração dos Dados
O script 01_baixar_dados.py verifica se o arquivo já existe e faz o download se necessário.

<img width="1594" height="355" alt="image" src="https://github.com/user-attachments/assets/2d5a39b6-08c8-43ab-a98e-29d54bb9b717" />


Resultado: ✅ train.csv baixado com sucesso (29,69 MB)

2. Transformação e Limpeza
O script 03_limpar_dados.py processa 100.000 registros, remove dados inconsistentes e gera 11.811 registros limpos.

<img width="1522" height="918" alt="image" src="https://github.com/user-attachments/assets/0d18b0e0-6278-4770-88ed-8a87f22b0994" />
<img width="1161" height="930" alt="image" src="https://github.com/user-attachments/assets/a2838484-ee5e-4650-9668-dfa8aa8a7fd5" />
<img width="1026" height="910" alt="image" src="https://github.com/user-attachments/assets/949ce73c-fb51-4b13-afcf-1423e09cf8ea" />



Resultado:

✅ 11.811 registros limpos

✅ 32 colunas (5 novas features)

✅ Distribuição dos scores: Standard 55,5%, Poor 27,7%, Good 16,8%

3. Arquivos Gerados
Todos os arquivos processados são salvos na pasta dados/processed/.

<img width="432" height="387" alt="image" src="https://github.com/user-attachments/assets/dee3b6f2-4d1a-4184-b102-45091609f207" />


Arquivos gerados:

dados_prontos.csv (11.811 registros)

dashboard_score.csv (resumo por score)

dashboard_risco.csv (resumo por risco)

dashboard_idade.csv (resumo por idade)

relatorio_validacao.json (validações)

resumo_final.json (estatísticas finais)

4. Pipeline Automatizado
O script 05_pipeline_automatizado.py executa todo o pipeline em sequência, simulando o agendamento do Airflow.

<img width="1669" height="1061" alt="image" src="https://github.com/user-attachments/assets/5b86904f-556c-4bb6-843f-6b255b3144b1" />


Resultado:

✅ Extração: concluída (0,7s)

✅ Transformação: concluída (1,4s)

✅ Carga: concluída (0,7s)

✅ Pipeline executado com sucesso!

5. Dashboard Power BI
Visualização final dos dados processados no Power BI.

<img width="1931" height="1075" alt="image" src="https://github.com/user-attachments/assets/e05bc973-7596-4f9d-a357-f06c49f7f799" />


Visuais do dashboard:

Total de Clientes: 11.766

Distribuição dos Scores: Bom 16,85% | Médio 55,46% | Ruim 27,70%

Renda Média por Score: Análise comparativa

Risco por Score: Distribuição de risco por categoria

📝 Perguntas Norteadoras
1. Como garantir dados atualizados?
O pipeline é automatizado com agendamento diário (simulado via script 05_pipeline_automatizado.py), garantindo que os dados sejam extraídos, processados e disponibilizados regularmente.

Solução implementada:

Execução em sequência dos 3 principais scripts

Verificação de existência de arquivos antes do download

Logs detalhados de cada etapa

2. Quais validações de qualidade dos dados?
Foram implementadas diversas validações durante o processo de transformação:

Validação	Descrição
Idade	Entre 18-100 anos
Renda	Valores não negativos
Score	Apenas Good/Standard/Poor
Duplicatas	Removidas por Customer_ID
Nulos	Tratados com valores padrão
Tipos	Conversão para tipos corretos
3. Como evitar duplicatas?
A estratégia de deduplicação inclui:

Remoção por chave única: Customer_ID como identificador único

Particionamento: Dados organizados por Credit_Score

Versionamento: Arquivos com data de processamento

4. Como organizar para análises?
A organização dos dados foi pensada para facilitar consultas e dashboards:

Formato: CSV (compatível com Power BI)

Particionamento: Por Credit_Score e data

Versões simplificadas: Para agilizar visualizações

Métricas agregadas: Total, médias e distribuições

📊 Dashboard Power BI
O dashboard criado no Power BI apresenta visualizações interativas para análise de crédito:

Visuais incluídos
Visual	Descrição
Cartão	Total de clientes (11.766)
Rosca	Distribuição dos scores de crédito
Barras	Renda média por categoria de score
Barras Empilhadas	Risco de pagamento por score
Como acessar
Baixe o arquivo dashboard/dashboard_credit_score.pbix

Abra no Power BI Desktop (gratuito)

Os dados já estão conectados automaticamente

👩‍💻 Autora
Anaya Felix - Bootcamp [RE]Start - Trilha Engenharia de Dados


📅 Data de Entrega
12/07/2026


🙏 Agradecimentos
Bootcamp [RE]Start - Pela oportunidade e aprendizado

Data Girls Finance - Pelo desafio proposto

Kaggle - Pelo dataset disponibilizado

📚 Referências
Dataset Credit Score Classification

Documentação Pandas

Power BI Desktop

Kaggle API
