# 📊 Dashboard de Análise de Salários na Área de Dados - Aula 04

## 🎯 Sobre o Projeto

Este projeto representa o culminar da **Imersão Ciência de Dados com Python da Alura**, onde desenvolvemos um dashboard interativo para análise de salários na área de dados. A aplicação foi construída utilizando **Streamlit** e está disponível online em: [https://idc-python-alura.streamlit.app/](https://idc-python-alura.streamlit.app/)

## 🚀 Aplicação em Produção

**URL da Aplicação:** https://idc-python-alura.streamlit.app/

A aplicação foi publicada no **Streamlit Community Cloud**, demonstrando o processo completo de desenvolvimento e deploy de uma aplicação de ciência de dados.

## 📁 Estrutura do Projeto

```
Aula-04/
├── app.py                          # Aplicação principal Streamlit
├── requirements.txt                # Dependências do projeto
├── dados-imersao-final-Dia04.csv  # Dataset local (backup)
├── AmbienteConfiguracao           # Instruções de configuração
└── README.md                      # Este arquivo
```

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Streamlit 1.44.1** - Framework para criação de aplicações web
- **Pandas 2.2.3** - Manipulação e análise de dados
- **Plotly 5.24.1** - Visualizações interativas

## 📊 Funcionalidades do Dashboard

### 🔍 Filtros Interativos
- **Ano**: Filtro por período temporal
- **Senioridade**: Junior, Pleno, Senior
- **Tipo de Contrato**: Integral, meio período, freelance
- **Tamanho da Empresa**: Pequena, média, grande

### 📈 Métricas Principais (KPIs)
- Salário médio anual (USD)
- Salário máximo registrado
- Total de registros analisados
- Cargo mais frequente

### 📊 Visualizações Implementadas

1. **Gráfico de Barras Horizontais**: Top 10 cargos por salário médio
2. **Histograma**: Distribuição de salários anuais
3. **Gráfico de Pizza**: Proporção dos tipos de trabalho (remoto/presencial/híbrido)
4. **Mapa Coroplético**: Salário médio de Cientistas de Dados por país

### 📋 Tabela de Dados Detalhados
Visualização completa dos dados filtrados com todas as colunas disponíveis.

## 🗃️ Dataset

O dataset contém informações sobre salários na área de dados com as seguintes colunas:

- `ano`: Ano do registro
- `senioridade`: Nível de experiência (junior, pleno, senior)
- `contrato`: Tipo de contrato de trabalho
- `cargo`: Função/cargo exercido
- `salario`: Salário na moeda original
- `moeda`: Moeda do salário
- `usd`: Salário convertido para USD
- `residencia`: País de residência
- `remoto`: Modalidade de trabalho
- `empresa`: País da empresa
- `tamanho_empresa`: Porte da empresa
- `genero`: Gênero do profissional
- `residencia_iso3`: Código ISO3 do país

**Fonte dos dados**: Dataset hospedado no GitHub para garantir disponibilidade online.

## 🚀 Como Executar Localmente

### Pré-requisitos
- Python 3.x instalado
- pip (gerenciador de pacotes Python)

### Passos para Execução

1. **Clone ou baixe o projeto**
```bash
cd Aula-04
```

2. **Crie um ambiente virtual (recomendado)**
```bash
python3 -m venv .venv
source .venv/bin/activate  # Linux/Mac
# ou
.venv\Scripts\activate     # Windows
```

3. **Instale as dependências**
```bash
pip install -r requirements.txt
```

4. **Execute a aplicação**
```bash
streamlit run app.py
```

5. **Acesse no navegador**
```
http://localhost:8501
```

## 🌐 Deploy no Streamlit Community Cloud

### Processo de Publicação

1. **Preparação do Repositório**
   - Código organizado em repositório GitHub
   - Arquivo `requirements.txt` com dependências
   - Dataset acessível via URL pública

2. **Configuração no Streamlit Cloud**
   - Conectar conta GitHub
   - Selecionar repositório e branch
   - Definir arquivo principal (`app.py`)

3. **Deploy Automático**
   - Build automático a cada commit
   - URL pública gerada automaticamente
   - Monitoramento de logs em tempo real

## 🎓 Aprendizados da Aula 04

### Conceitos Abordados

1. **Desenvolvimento de Dashboard Interativo**
   - Estruturação de layout com Streamlit
   - Implementação de filtros dinâmicos
   - Criação de métricas (KPIs)

2. **Visualizações Avançadas com Plotly**
   - Gráficos interativos e responsivos
   - Mapas coropléticos para dados geográficos
   - Customização de aparência e layout

3. **Boas Práticas de Desenvolvimento**
   - Organização de código modular
   - Tratamento de dados vazios
   - Interface responsiva

4. **Deploy e Publicação**
   - Processo de deploy no Streamlit Community Cloud
   - Configuração de dependências
   - Gestão de dados externos

### Técnicas Implementadas

- **Filtragem Dinâmica**: Sistema de filtros que atualiza todos os componentes
- **Layout Responsivo**: Uso de colunas para organização visual
- **Tratamento de Erros**: Validações para datasets vazios
- **Otimização de Performance**: Carregamento eficiente de dados

## 🔧 Configurações Técnicas

### Configuração da Página Streamlit
```python
st.set_page_config(
    page_title="Dashboard de Salários na Área de Dados",
    page_icon="📊",
    layout="wide",
)
```

### Carregamento de Dados
- Dados carregados via URL do GitHub para garantir disponibilidade
- Fallback para arquivo local em caso de problemas de conectividade

### Estrutura de Filtros
- Filtros implementados na barra lateral
- Seleção múltipla com valores padrão
- Aplicação automática de filtros no dataset

## 📈 Métricas e Análises

### KPIs Principais
- **Salário Médio**: Média aritmética dos salários filtrados
- **Salário Máximo**: Maior valor salarial no dataset filtrado
- **Total de Registros**: Quantidade de registros após aplicação dos filtros
- **Cargo Mais Frequente**: Moda dos cargos no dataset filtrado

### Análises Visuais
1. **Análise de Cargos**: Identificação dos cargos mais bem remunerados
2. **Distribuição Salarial**: Compreensão da dispersão dos salários
3. **Modalidade de Trabalho**: Proporção entre trabalho remoto, presencial e híbrido
4. **Análise Geográfica**: Comparação salarial entre países para Cientistas de Dados

## 🎯 Resultados e Insights

### Principais Descobertas
- Identificação dos cargos com maior remuneração média
- Análise da distribuição salarial na área de dados
- Compreensão das tendências de trabalho remoto
- Mapeamento geográfico das oportunidades

### Valor do Projeto
- **Ferramenta de Análise**: Dashboard funcional para análise de mercado
- **Aprendizado Prático**: Implementação completa de um projeto de dados
- **Portfolio**: Projeto publicado demonstrando competências técnicas

## 🔮 Próximos Passos

### Melhorias Possíveis
- Implementação de mais filtros (por exemplo, por gênero)
- Adição de análises temporais (evolução salarial ao longo dos anos)
- Implementação de comparações estatísticas
- Adição de exportação de dados filtrados
- Implementação de cache para melhor performance

### Expansões Futuras
- Integração com APIs de dados em tempo real
- Implementação de machine learning para predições salariais
- Adição de mais visualizações interativas
- Sistema de alertas para mudanças no mercado

## 👥 Créditos

- **Imersão Ciência de Dados com Python - Alura**
- **Instrutor**: [Nome do Instrutor]
- **Desenvolvido por**: Junior
- **Data**: Agosto de 2025

## 📞 Contato

Para dúvidas ou sugestões sobre este projeto, entre em contato através dos canais da Alura ou comunidade da Imersão.

---

**🎉 Parabéns por concluir a Imersão Ciência de Dados com Python!**

Este projeto representa não apenas o aprendizado técnico, mas também a capacidade de transformar dados em insights valiosos através de uma aplicação web interativa e acessível.
