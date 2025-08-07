# 🗺️ Explicação Detalhada - Código Python: Mapa Coroplético com Plotly

## 🎯 Sobre Este Documento

Este documento contém uma explicação **minuciosa e detalhada** do código Python que cria um **mapa coroplético interativo** para visualizar salários de Data Scientists por país usando **Plotly Express** e **pycountry**.

Este código representa um **nível avançado** de visualização geográfica de dados, demonstrando técnicas profissionais de **geolocalização** e **mapeamento de dados**.

---

## 📚 **Contexto e Objetivo do Código**

### **🎯 Objetivo Principal:**
Criar um **mapa mundial interativo** que mostra a distribuição salarial média de Data Scientists por país, usando cores para representar diferentes faixas salariais.

### **📊 Tipo de Visualização:**
**Mapa Coroplético** - mapa temático onde áreas geográficas são coloridas de acordo com valores estatísticos.

---

## 🔍 **Análise Detalhada Linha por Linha**

### **1. Função de Conversão de Códigos de País**

```python
# Função para converter ISO-2 para ISO-3
def iso2_to_iso3(code):
    try:
        return pycountry.countries.get(alpha_2=code).alpha_3
    except:
        return None
```

#### **🏷️ Definição da Função:**

| **Elemento** | **Explicação** |
|--------------|----------------|
| **`def iso2_to_iso3(code):`** | Define uma função que recebe um parâmetro `code` |
| **Nome da função** | `iso2_to_iso3` - nome descritivo da conversão que faz |
| **Parâmetro `code`** | Código de país no formato ISO-2 (ex: "US", "BR", "DE") |
| **Retorno** | Código de país no formato ISO-3 (ex: "USA", "BRA", "DEU") |

#### **🌍 Padrões ISO de Códigos de País:**

| **Padrão** | **Formato** | **Exemplo** | **Uso** |
|------------|-------------|-------------|---------|
| **ISO-2** | 2 letras | US, BR, DE, FR | Mais comum em datasets |
| **ISO-3** | 3 letras | USA, BRA, DEU, FRA | Requerido pelo Plotly para mapas |

#### **🔧 Funcionamento Interno:**

```python
try:
    return pycountry.countries.get(alpha_2=code).alpha_3
except:
    return None
```

**Explicação do bloco `try-except`:**

1. **`try:`** - Tenta executar o código que pode gerar erro
2. **`pycountry.countries.get(alpha_2=code)`** - Busca país pelo código ISO-2
3. **`.alpha_3`** - Acessa o atributo com código ISO-3 do país encontrado
4. **`except:`** - Se houver qualquer erro (país não encontrado, código inválido)
5. **`return None`** - Retorna `None` em caso de erro

#### **📋 Exemplos Práticos:**

```python
# Exemplos de funcionamento da função:
iso2_to_iso3("US")    # Retorna: "USA"
iso2_to_iso3("BR")    # Retorna: "BRA"
iso2_to_iso3("DE")    # Retorna: "DEU"
iso2_to_iso3("XX")    # Retorna: None (código inválido)
iso2_to_iso3(None)    # Retorna: None (entrada inválida)
```

#### **⚠️ Por que usar `try-except`?**

1. **🛡️ Proteção contra erros**: Códigos inválidos não quebram o programa
2. **🔄 Continuidade**: Processamento continua mesmo com dados problemáticos
3. **📊 Tratamento de dados sujos**: Datasets reais podem ter códigos incorretos
4. **🎯 Robustez**: Função funciona mesmo com entradas inesperadas

---

### **2. Aplicação da Função ao DataFrame**

```python
# Criar nova coluna com código ISO-3
df_limpo['residencia_iso3'] = df_limpo['residencia'].apply(iso2_to_iso3)
```

#### **🔧 Método `apply()` Explicado:**

| **Componente** | **Função** |
|----------------|------------|
| **`df_limpo['residencia']`** | Seleciona a coluna com códigos ISO-2 |
| **`.apply(iso2_to_iso3)`** | Aplica a função a cada valor da coluna |
| **`df_limpo['residencia_iso3']`** | Cria nova coluna com os resultados |

#### **📊 Transformação dos Dados:**

**Antes da aplicação:**
```
residencia
US
BR
DE
CA
```

**Depois da aplicação:**
```
residencia  residencia_iso3
US          USA
BR          BRA
DE          DEU
CA          CAN
```

#### **🔄 Processo Interno:**

1. **Iteração**: `apply()` percorre cada linha da coluna `residencia`
2. **Chamada da função**: Para cada valor, chama `iso2_to_iso3(valor)`
3. **Coleta de resultados**: Armazena todos os retornos em uma nova Series
4. **Atribuição**: Cria a nova coluna `residencia_iso3` com os resultados

---

### **3. Filtragem para Data Scientists**

```python
# Calcular média salarial por país (ISO-3)
df_ds = df_limpo[df_limpo['cargo'] == 'Data Scientist']
```

#### **🎯 Filtragem Booleana:**

| **Parte** | **Explicação** |
|-----------|----------------|
| **`df_limpo['cargo'] == 'Data Scientist'`** | Cria máscara booleana (True/False) |
| **`df_limpo[...]`** | Aplica a máscara para filtrar linhas |
| **`df_ds`** | Novo DataFrame apenas com Data Scientists |

#### **📊 Resultado da Filtragem:**

**DataFrame original (`df_limpo`):**
```
cargo                   residencia  usd
Data Scientist         US          150000
Software Engineer      BR          80000
Data Scientist         DE          120000
Product Manager        CA          110000
Data Scientist         FR          100000
```

**DataFrame filtrado (`df_ds`):**
```
cargo                   residencia  usd
Data Scientist         US          150000
Data Scientist         DE          120000
Data Scientist         FR          100000
```

---

### **4. Cálculo da Média Salarial por País**

```python
media_ds_pais = df_ds.groupby('residencia_iso3')['usd'].mean().reset_index()
```

#### **🔢 Operação `groupby()` Detalhada:**

| **Método** | **Função** |
|------------|------------|
| **`df_ds.groupby('residencia_iso3')`** | Agrupa dados por país (ISO-3) |
| **`['usd']`** | Seleciona apenas a coluna de salários |
| **`.mean()`** | Calcula a média para cada grupo |
| **`.reset_index()`** | Transforma o resultado em DataFrame normal |

#### **📊 Processo de Agrupamento:**

**Dados de entrada (`df_ds`):**
```
residencia_iso3  usd
USA              150000
USA              180000
USA              160000
BRA              70000
BRA              80000
DEU              120000
DEU              130000
```

**Após `groupby().mean()`:**
```
residencia_iso3
USA    163333.33
BRA     75000.00
DEU    125000.00
```

**Após `reset_index()`:**
```
residencia_iso3      usd
USA              163333.33
BRA               75000.00
DEU              125000.00
```

#### **🎯 Por que `reset_index()`?**

1. **📊 Estrutura de DataFrame**: Converte Series indexada em DataFrame
2. **🔧 Compatibilidade**: Plotly precisa de colunas nomeadas
3. **📋 Facilidade de uso**: Permite acessar dados como `df['coluna']`

---

### **5. Criação do Mapa Coroplético**

```python
# Gerar o mapa
fig = px.choropleth(media_ds_pais,
                    locations='residencia_iso3',
                    color='usd',
                    color_continuous_scale='rdylgn',
                    title='Salário médio de Cientista de Dados por país',
                    labels={'usd': 'Salário médio (USD)', 'residencia_iso3': 'País'})
```

#### **🗺️ Função `px.choropleth()` Explicada:**

| **Parâmetro** | **Valor** | **Função** |
|---------------|-----------|------------|
| **DataFrame** | `media_ds_pais` | Dados para o mapa |
| **`locations`** | `'residencia_iso3'` | Coluna com códigos de país |
| **`color`** | `'usd'` | Coluna que define as cores |
| **`color_continuous_scale`** | `'rdylgn'` | Escala de cores |
| **`title`** | `'Salário médio...'` | Título do mapa |
| **`labels`** | `{...}` | Renomeação de labels |

#### **🎨 Escala de Cores `'rdylgn'`:**

| **Cor** | **Significado** | **Valor Salarial** |
|---------|-----------------|-------------------|
| **🔴 Vermelho** | Salários mais baixos | Valores mínimos |
| **🟡 Amarelo** | Salários médios | Valores intermediários |
| **🟢 Verde** | Salários mais altos | Valores máximos |

#### **🏷️ Parâmetro `labels` Detalhado:**

```python
labels={'usd': 'Salário médio (USD)', 'residencia_iso3': 'País'}
```

**Função:**
- **`'usd': 'Salário médio (USD)'`**: Renomeia coluna na legenda
- **`'residencia_iso3': 'País'`**: Renomeia coluna nos tooltips

---

### **6. Exibição do Mapa**

```python
fig.show()
```

#### **📱 Funcionalidades Interativas:**

1. **🔍 Zoom**: Aproximar/afastar regiões
2. **🖱️ Pan**: Arrastar para navegar
3. **📊 Hover**: Informações ao passar o mouse
4. **🎨 Legenda**: Escala de cores interativa
5. **💾 Export**: Salvar como imagem

---

## 🔧 **Dependências e Bibliotecas Necessárias**

### **📦 Importações Requeridas:**

```python
import plotly.express as px
import pycountry
import pandas as pd
```

#### **📚 Explicação das Bibliotecas:**

| **Biblioteca** | **Função** | **Uso no Código** |
|----------------|------------|-------------------|
| **`plotly.express`** | Visualizações interativas | Criar o mapa coroplético |
| **`pycountry`** | Dados de países | Converter códigos ISO-2 para ISO-3 |
| **`pandas`** | Manipulação de dados | DataFrames e operações de dados |

#### **💻 Instalação:**

```bash
pip install plotly pycountry pandas
```

---

## 🎯 **Conceitos Técnicos Aplicados**

### **1. 🗺️ Cartografia Digital:**

- **Mapa Coroplético**: Representação temática com cores
- **Projeção Geográfica**: Plotly usa projeção padrão
- **Códigos ISO**: Padrão internacional para países

### **2. 📊 Análise de Dados Geoespaciais:**

- **Agregação Geográfica**: Média por país
- **Visualização Temática**: Cores representam valores
- **Interatividade**: Exploração dinâmica dos dados

### **3. 🔧 Programação Defensiva:**

- **Tratamento de Erros**: `try-except` para robustez
- **Validação de Dados**: Verificação de códigos de país
- **Fallback**: Retorno de `None` para casos problemáticos

---

## 📈 **Vantagens desta Abordagem**

### **✅ Benefícios Técnicos:**

1. **🌍 Visualização Geográfica**: Padrões espaciais claros
2. **🎨 Representação Intuitiva**: Cores facilitam interpretação
3. **📱 Interatividade**: Exploração dinâmica dos dados
4. **🔧 Robustez**: Tratamento de erros e dados problemáticos
5. **📊 Escalabilidade**: Funciona com qualquer número de países

### **💼 Aplicações Profissionais:**

1. **📈 Relatórios Executivos**: Visualizações impactantes
2. **🌐 Análise de Mercado**: Comparação internacional
3. **💰 Benchmarking Salarial**: Posicionamento competitivo
4. **🎯 Tomada de Decisão**: Insights geográficos claros

---

## ⚠️ **Limitações e Considerações**

### **🚨 Limitações Técnicas:**

1. **📊 Dados Ausentes**: Países sem dados aparecem em branco
2. **🔢 Tamanho da Amostra**: Médias podem ser baseadas em poucos dados
3. **🌍 Cobertura Geográfica**: Limitada aos países no dataset
4. **💱 Conversão Monetária**: Valores em USD podem não refletir poder de compra

### **⚖️ Considerações Metodológicas:**

1. **📈 Representatividade**: Amostra pode não ser representativa
2. **⏰ Temporalidade**: Dados podem estar desatualizados
3. **🎯 Contexto**: Diferenças de custo de vida não consideradas
4. **📊 Outliers**: Valores extremos podem distorcer médias

---

## 🚀 **Extensões e Melhorias Possíveis**

### **📊 Melhorias nos Dados:**

```python
# Adicionar informações estatísticas
media_ds_pais_completo = df_ds.groupby('residencia_iso3')['usd'].agg([
    'mean', 'median', 'std', 'count'
]).reset_index()

# Filtrar países com amostra mínima
media_ds_pais_filtrado = media_ds_pais_completo[
    media_ds_pais_completo['count'] >= 5
]
```

### **🎨 Melhorias Visuais:**

```python
# Personalização avançada do mapa
fig = px.choropleth(
    media_ds_pais,
    locations='residencia_iso3',
    color='usd',
    color_continuous_scale='rdylgn',
    title='<b>Salário Médio de Data Scientists por País</b><br><sup>Valores em USD (2025)</sup>',
    labels={'usd': 'Salário Médio (USD)', 'residencia_iso3': 'País'},
    hover_data=['count'],  # Mostrar número de amostras
    range_color=[50000, 200000]  # Definir range de cores
)

# Personalizar layout
fig.update_layout(
    title_x=0.5,  # Centralizar título
    geo=dict(
        showframe=False,
        showcoastlines=True,
        projection_type='equirectangular'
    )
)
```

### **📱 Interatividade Avançada:**

```python
# Adicionar dropdown para diferentes métricas
fig.update_layout(
    updatemenus=[
        dict(
            buttons=list([
                dict(label="Média", method="restyle", args=["z", [media_data]]),
                dict(label="Mediana", method="restyle", args=["z", [median_data]]),
                dict(label="Máximo", method="restyle", args=["z", [max_data]])
            ]),
            direction="down",
            showactive=True,
        ),
    ]
)
```

---

## 🎓 **Conceitos de Data Science Demonstrados**

### **📊 Análise Exploratória de Dados:**

1. **🔍 Filtragem**: Seleção de subconjuntos relevantes
2. **📈 Agregação**: Cálculo de estatísticas por grupo
3. **🗺️ Visualização Geográfica**: Representação espacial de dados
4. **🎨 Storytelling**: Comunicação visual de insights

### **🔧 Engenharia de Dados:**

1. **🔄 Transformação**: Conversão de códigos de país
2. **🛡️ Tratamento de Erros**: Programação defensiva
3. **📋 Padronização**: Uso de padrões internacionais (ISO)
4. **🔗 Integração**: Combinação de múltiplas fontes de dados

---

## 📝 **Conclusão**

Este código representa um **exemplo excepcional** de visualização geográfica de dados, demonstrando:

### **🎯 Competências Técnicas:**

- **🗺️ Cartografia Digital**: Criação de mapas temáticos profissionais
- **🔧 Programação Robusta**: Tratamento adequado de erros e casos extremos
- **📊 Análise Geoespacial**: Agregação e visualização de dados por localização
- **🎨 Design de Informação**: Uso efetivo de cores para comunicar insights

### **💼 Valor Profissional:**

- **📈 Relatórios Executivos**: Visualizações impactantes para tomada de decisão
- **🌐 Análise Internacional**: Comparação de mercados globais
- **💰 Inteligência Salarial**: Benchmarking competitivo
- **🎯 Comunicação de Dados**: Storytelling visual efetivo

### **🚀 Evolução do Aprendizado:**

Este código demonstra um **nível avançado** de competência em Data Science, integrando:
- **Manipulação de dados complexa**
- **Visualização geográfica interativa**
- **Programação defensiva**
- **Padrões internacionais**
- **Design de informação profissional**

**É um exemplo perfeito de como transformar dados brutos em insights visuais poderosos e acionáveis!** 🌍📊✨

---

## 👨‍💻 **Informações do Projeto**

- **Curso**: Imersão Dados com Python - Alura
- **Aula**: 3 - Visualização Avançada de Dados
- **Técnica**: Mapa Coroplético com Plotly Express
- **Data**: 07/08/2025
- **Autor**: Junior Fernandes
- **Arquivo Original**: `Aula3_ImersaoPythonDeverCasa.ipynb`

---

⭐ **Este documento demonstra a evolução para visualizações geográficas profissionais em Data Science!**

📚 **Para mais informações, consulte o [README.md](./README.md) do projeto.**
