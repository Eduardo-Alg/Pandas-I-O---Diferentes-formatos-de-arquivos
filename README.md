# 🐼 Estudo de Leitura e Escrita de CSV com Pandas

Projeto realizado no Google Colab como parte dos estudos de manipulação de dados com a biblioteca **Pandas**. O foco foi aprender a **ler arquivos CSV**, configurar parâmetros da leitura e **salvar DataFrames em CSV** com controle total.

---

## 📚 Conteúdo

- Leitura de CSV com `read_csv()`
- Parâmetros úteis: `sep`, `nrows`, `usecols`, `encoding`
- Escrita de CSV com `to_csv()`
- Problema da coluna "Unnamed" e como evitar `index=False`
- Leitura de arquivo salvo no ambiente local (Colab)

---

## 🧪 Execução

### 1. Importar biblioteca
import pandas as pd

### 2. Ler arquivo CSV padrão (vírgula)
url = 'https://raw.githubusercontent.com/alura-cursos/Pandas/main/superstore_data.csv'
dados = pd.read_csv(url)

### 3. Ler CSV com separador ponto e vírgula
url_2 = 'https://raw.githubusercontent.com/alura-cursos/Pandas/main/superstore_data_ponto_virgula.csv'
dados_ponto_virgula = pd.read_csv(url_2, sep=';') 

### 4. Ler apenas algumas linhas
dados_linhas = pd.read_csv(url, nrows=5)

### 5. Selecionar colunas por nome
dados_colunas = pd.read_csv(url, usecols=['Id', 'Year_Birth', 'Income'])

### 6. Selecionar colunas por posição (índice)
dados_colunas = pd.read_csv(url, usecols=[0, 1, 4])

### 7. Salvar CSV sem índice (para evitar coluna "Unnamed")
dados_colunas.to_csv('clientes_mercado.csv', index=False)

### 8. Ler CSV salvo localmente no Colab
clientes_mercado = pd.read_csv('/content/clientes_mercado.csv')

🧠 Observações Cruciais
- Sempre use index=False ao salvar CSV, caso contrário uma coluna extra ("Unnamed") será criada.

- Use sep=';' apenas se o arquivo for separado por ponto e vírgula.

- Use usecols para trazer apenas as colunas necessárias, economizando memória e tempo.

- nrows é útil para carregar apenas uma amostra do dataset.

🛠️ Ambiente
- Python 3.x

- Pandas

- Google Colab

📎 Fonte dos dados
- Dados fictícios da Alura: superstore_data.csv

✅ Status
🚧 Estudo em andamento — próximo passo: leitura e escrita de arquivos Excel com Pandas.

