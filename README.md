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

## 🚀 Aula 1 - Primeiros Passos com Python e Pandas

### 📋 Objetivos da Aula

Na primeira aula da imersão, exploramos os fundamentos do Python para análise de dados, com foco em:

- Introdução ao ambiente Python
- Manipulação de datas e horários
- Carregamento e exploração inicial de datasets
- Primeiras análises com Pandas
- Limpeza e transformação de dados

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

- Visualização de dados com Matplotlib e Seaborn
- Análises estatísticas mais avançadas
- Criação de dashboards interativos
- Machine Learning aplicado aos dados
- Storytelling com dados

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

---

⭐ **Gostou do projeto?** Deixe uma estrela no repositório!

📚 **Quer aprender mais?** Confira os cursos da [Escola de Data Science da Alura](https://www.alura.com.br/escola-data-science)
