# 📊 Imersão Dados com Python - Alura

## 🎯 Sobre o Projeto

Este repositório contém os materiais e análises desenvolvidos durante a **Imersão Dados com Python** da Alura. O projeto foca na análise exploratória de dados de salários em tecnologia, utilizando Python e suas principais bibliotecas para ciência de dados.

**Link do evento:** [Imersão Dados com Python - Guia de Mergulho](https://grupoalura.notion.site/Imers-o-Dados-com-Python-Guia-de-Mergulho-226379bdd09b808ca2e3d4d95a56b1ce#237379bdd09b80b78c16e079289ad6dd)

## 📁 Estrutura do Projeto

```
idcPython-alura/
├── README.md                                    # Este arquivo
├── Aula1_ImersaoPython.ipynb                   # Notebook da primeira aula
├── Roteiro_Imersão_Dados_com_Python.ipynb      # Roteiro completo da imersão
├── salaries.csv                                 # Dataset de salários em tecnologia
├── LinksPythonAprender                          # Links úteis para aprendizado
└── .gitignore                                   # Arquivos ignorados pelo Git
```

## 🚀 Evolução do Aprendizado - Aulas 1, 2 e 3

### 📋 Aula 1 - Primeiros Passos com Python e Pandas

Na primeira aula da imersão, exploramos os fundamentos do Python para análise de dados, com foco em:

- ✅ Introdução ao ambiente Python
- ✅ Manipulação de datas e horários
- ✅ Carregamento e exploração inicial de datasets
- ✅ Primeiras análises com Pandas
- ✅ Limpeza e transformação de dados básica

### 🎯 Aula 2 - Aprofundamento em Limpeza e Tratamento de Dados

Na segunda aula, expandimos nossos conhecimentos com técnicas avançadas de tratamento de dados:

- ✅ **Tratamento de valores ausentes (NaN)** com múltiplas estratégias
- ✅ **Preenchimento por média e mediana** usando `fillna()`
- ✅ **Forward Fill (ffill)** e **Backward Fill (bfill)** para dados temporais
- ✅ **Preenchimento personalizado** com valores específicos
- ✅ **Remoção de linhas com dados ausentes** usando `dropna()`
- ✅ **Conversão de tipos de dados** para otimização de memória
- ✅ **Criação de DataFrames de exemplo** para validação de métodos

### 📊 Aula 3 - Visualização Avançada de Dados

Na terceira aula, demos um salto significativo na apresentação e análise visual dos dados:

- ✅ **Visualização interativa com Plotly** (`plotly.express` e `plotly.graph_objects`)
- ✅ **Múltiplos tipos de gráficos**: barras, pizza, donut, subplots
- ✅ **Análise comparativa por países** com destaque para Data Scientists
- ✅ **Gráficos temáticos personalizados** (tema escuro, cores customizadas)
- ✅ **Interatividade avançada** com hover templates e formatação
- ✅ **Storytelling com dados** através de visualizações profissionais
- ✅ **Análise de distribuição salarial** por diferentes dimensões
- ✅ **Técnicas de agrupamento e agregação** para insights visuais

### 🔄 Comparação da Evolução

| Aspecto | Aula 1 | Aula 2 | Aula 3 |
|---------|--------|--------|--------|
| **Foco Principal** | Exploração e análise básica | Limpeza e tratamento avançado | Visualização e storytelling |
| **Bibliotecas** | `pandas`, `datetime` | `pandas`, `numpy` | `pandas`, `plotly.express`, `plotly.graph_objects` |
| **Tratamento de Dados** | Renomeação e substituição | Múltiplas estratégias para NaN | Agrupamento e agregação para visualização |
| **Complexidade** | Iniciante | Intermediário | Avançado |
| **Técnicas Novas** | `value_counts()`, `replace()` | `fillna()`, `dropna()`, `ffill()`, `bfill()` | `px.bar()`, `px.pie()`, `go.Figure()`, `make_subplots()` |
| **Output** | Análises textuais | DataFrames limpos | Gráficos interativos profissionais |

## 🌱 A Importância do Aprendizado Contínuo

### 💡 Reflexões sobre a Evolução

A comparação entre as Aulas 1, 2 e 3 demonstra claramente como o **aprendizado contínuo** é fundamental na jornada de Data Science:

#### 🔍 **Progressão Natural do Conhecimento**
- **Aula 1**: Estabeleceu as bases com conceitos fundamentais
- **Aula 2**: Construiu sobre essa base, introduzindo técnicas mais sofisticadas
- **Aula 3**: Elevou o nível com visualizações interativas e storytelling profissional
- **Resultado**: Cada nova aula amplia exponencialmente o repertório de ferramentas disponíveis

#### 🛠️ **Complexidade Crescente**
```python
# Aula 1: Análise básica
df['senioridade'].value_counts()

# Aula 2: Tratamento avançado de dados ausentes
df_salarios['salario_media'] = df_salarios['salario'].fillna(df_salarios['salario'].mean().round(2))
df_temperatura['preenchido_ffill'] = df_temperatura['temperatura'].fillna(method='ffill')

# Aula 3: Visualizações interativas profissionais
import plotly.express as px
import plotly.graph_objects as go
from plotly.subplots import make_subplots

fig = px.bar(df_grouped, x='pais', y='salario_medio', 
             title='Salário Médio por País com Destaque para Data Scientists',
             hover_data=['quantidade'])
fig.show()
```

#### 🎯 **Benefícios do Aprendizado Incremental**

1. **Consolidação**: Cada aula reforça conceitos anteriores
2. **Aplicação Prática**: Novos métodos são aplicados em cenários reais
3. **Confiança**: Progressão gradual constrói segurança técnica
4. **Versatilidade**: Múltiplas abordagens para resolver problemas similares
5. **Storytelling**: Capacidade de comunicar insights através de visualizações impactantes

#### 🚀 **Mindset de Crescimento**

> *"O aprendizado em Data Science não é um destino, mas uma jornada contínua. Cada dataset apresenta novos desafios, cada projeto demanda novas soluções."*

**Características do Aprendizado Contínuo em Data Science:**
- **Adaptabilidade**: Tecnologias e métodos evoluem constantemente
- **Curiosidade**: Sempre há uma nova biblioteca, técnica ou abordagem para explorar
- **Prática**: Conhecimento teórico só se consolida com aplicação prática
- **Comunidade**: Aprender com outros profissionais acelera o desenvolvimento

#### 📈 **Próximos Passos na Jornada**

A evolução das aulas 1, 2 e 3 prepara o terreno para conceitos ainda mais avançados:
- ✅ **Visualização de dados interativa** (concluído na Aula 3)
- 🔄 **Análises estatísticas complexas**
- 🔄 **Machine Learning aplicado**
- 🔄 **Storytelling avançado com dados**
- 🔄 **Dashboards interativos**
- 🔄 **Análise preditiva**

### 🎓 **Lições Aprendidas**

1. **Cada conceito é um tijolo**: Construindo uma base sólida passo a passo
2. **Prática leva à perfeição**: Repetição e aplicação consolidam o aprendizado
3. **Erros são oportunidades**: Cada desafio enfrentado fortalece o conhecimento
4. **Comunidade importa**: Compartilhar conhecimento acelera o crescimento de todos

### 🔍 Dataset Analisado

**Fonte:** [Data Jobs Salaries Dataset](https://raw.githubusercontent.com/guilhermeonrails/data-jobs/refs/heads/main/salaries.csv)

**Características do Dataset:**
- **133.349 registros** de salários em tecnologia
- **11 colunas** com informações detalhadas
- Período: 2020-2025
- Dados globais de diferentes países e moedas

### 📊 Principais Descobertas

#### Distribuição por Senioridade
- **Senior (SE):** 77.241 profissionais (57,9%)
- **Pleno (MI):** 40.465 profissionais (30,3%)
- **Júnior (EN):** 12.443 profissionais (9,3%)
- **Executivo (EX):** 3.200 profissionais (2,4%)

#### Tipos de Contrato
- **Integral (FT):** 132.563 contratos (99,4%)
- **Contrato (CT):** 394 contratos (0,3%)
- **Parcial (PT):** 376 contratos (0,3%)
- **Freelancer (FL):** 16 contratos (0,01%)

#### Tamanho das Empresas
- **Média:** 129.561 empresas (97,2%)
- **Pequena:** 2.538 empresas (1,9%)
- **Grande:** 1.250 empresas (0,9%)

#### Modalidade de Trabalho
- **Presencial:** 105.312 posições (79,0%)
- **Remoto:** 27.037 posições (20,3%)
- **Híbrido:** 1.000 posições (0,7%)

### 💰 Estatísticas Salariais

- **Salário médio:** $157.617 USD
- **Salário mediano:** $146.206 USD
- **Faixa salarial:** $15.000 - $800.000 USD
- **Cargo mais comum:** Data Scientist (17.314 ocorrências)
- **País predominante:** Estados Unidos (119.579 registros)

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pandas** - Manipulação e análise de dados
- **Datetime** - Manipulação de datas e horários
- **Google Colab** - Ambiente de desenvolvimento

## 📚 Conceitos Aprendidos

### 1. Manipulação de Datas
```python
from datetime import date, datetime, timezone

# Data atual
data_atual = date.today()

# Formatação de datas
data_formatada = data_atual.strftime("%d/%m/%Y")

# Conversão de strings para datetime
data_convertida = datetime.strptime("01/03/2018 12:30", "%d/%m/%Y %H:%M")
```

### 2. Análise Exploratória com Pandas
```python
import pandas as pd

# Carregamento dos dados
df = pd.read_csv("url_do_dataset")

# Informações básicas
df.info()
df.describe()
df.shape

# Análise de valores únicos
df['coluna'].value_counts()
```

### 3. Limpeza e Transformação de Dados
```python
# Renomeação de colunas
novos_nomes = {
    'work_year': 'ano',
    'experience_level': 'senioridade',
    'employment_type': 'contrato'
}
df.rename(columns=novos_nomes, inplace=True)

# Substituição de valores
mapeamento_senioridade = {
    'SE': 'senior',
    'MI': 'pleno',
    'EN': 'junior',
    'EX': 'executivo'
}
df['senioridade'] = df['senioridade'].replace(mapeamento_senioridade)
```

## 🎯 Próximos Passos

As próximas aulas da imersão abordarão:

- ✅ Visualização de dados com Plotly (concluído na Aula 3)
- Análises estatísticas mais avançadas
- Criação de dashboards interativos
- Machine Learning aplicado aos dados
- Storytelling avançado com dados

## 📖 Recursos de Aprendizado

### Links Úteis (disponíveis no arquivo `LinksPythonAprender`)

- [Artigos Python - Alura](https://www.alura.com.br/artigos/python)
- [Lidando com Datas e Horários no Python](https://www.alura.com.br/artigos/lidando-com-datas-e-horarios-no-python)
- [Pandas: O que é, para que serve e como instalar](https://www.alura.com.br/artigos/pandas-o-que-e-para-que-serve-como-instalar)
- [Data Visualization: Conhecendo bibliotecas Python](https://www.alura.com.br/artigos/data-visualization-conhecendo-bibliotecas-python)
- [O que é Git e GitHub](https://www.alura.com.br/artigos/o-que-e-git-github)

### Ambientes Virtuais
```bash
# Criando ambiente virtual
python -m venv nome_do_ambiente

# Ativando (Linux/Mac)
source nome_do_ambiente/bin/activate

# Ativando (Windows)
nome_do_ambiente\Scripts\activate

# Desativando
deactivate
```

## 🤝 Contribuições

Este é um projeto de aprendizado da Imersão Dados com Python da Alura. Sinta-se à vontade para:

- Fazer fork do projeto
- Sugerir melhorias
- Compartilhar suas próprias análises
- Reportar issues

## 📄 Licença

Este projeto é desenvolvido para fins educacionais como parte da Imersão Dados com Python da Alura.

## 👨‍💻 Autor

**Junior Fernandes**

- Participante da Imersão Dados com Python - Alura
- Data de conclusão da Aula 1: 05/08/2025
- Data de conclusão da Aula 2: 06/08/2025
- Data de conclusão da Aula 3: 07/08/2025
- Data de conclusão da Aula 4: 08/08/2025

---

⭐ **Gostou do projeto?** Deixe uma estrela no repositório!

📚 **Quer aprender mais?** Confira os cursos da [Escola de Data Science da Alura](https://www.alura.com.br/escola-data-science)
