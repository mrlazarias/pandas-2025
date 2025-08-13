# 📅 Dia 1: Fundamentos do Pandas

> 🎯 **Objetivo**: Conhecer os conceitos básicos do Pandas e trabalhar com Series

## 🧠 O que Aprendemos Hoje

### 1. 🐼 Primeiro Contato com Pandas
- Importação da biblioteca pandas
- Criação de Series vazias
- Entendimento da estrutura básica do pandas

### 2. 📊 Trabalhando com Series
- **Conceito**: Series são arrays unidimensionais rotulados
- **Criação**: Como transformar listas Python em Series do pandas
- **Vantagens**: Métodos estatísticos integrados

### 3. 🎯 Indexação e Seleção de Dados
- **Indexação posicional**: `.iloc[]` para acessar por posição
- **Indexação por rótulos**: Usando índices personalizados
- **Slicing**: Fatiar dados com `[:]`
- **Ordenação**: `.sort_values()` para organizar dados

### 4. 📋 Introdução aos DataFrames
- **Conceito**: DataFrames são tabelas com linhas e colunas
- **Criação**: Combinando múltiplas Series
- **Estrutura**: Dados organizados em formato tabular
- **Acesso**: Seleção de linhas e colunas específicas

## 💻 Códigos Desenvolvidos

### 📝 `01_hello_pandas.py`
```python
import pandas as pd
pd.Series()  # Criando uma Series vazia
```

**Aprendizado**: Primeiro contato com a biblioteca pandas e criação de objetos Series.

### 📝 `02_series.py`
```python
# Cálculo manual de estatísticas
idades = [32, 38, 30, 30, 31, 35, 25, 29, 31, 37, 27, 23, 36, 33, 32]

# Média manual
media = sum(idades) / len(idades)

# Variância manual
diffs = 0
for i in idades:
    diffs += (i - media) ** 2
variancia = diffs / (len(idades)-1)

# Agora com pandas - MUITO mais fácil!
import pandas as pd
series_idades = pd.Series(idades)

# Estatísticas automáticas
media_idades = series_idades.mean()
var_idades = series_idades.var()
summary_idades = series_idades.describe()
```

**Aprendizado**: Comparação entre cálculos manuais vs métodos do pandas. Descoberta dos "superpoderes" estatísticos das Series.

### 📝 `03_series_index.py.py`
```python
import pandas as pd

idades = [32, 38, 30, 30, 31, 35, 25, 29, 31, 37, 27, 23, 36, 33, 39]
series_idades = pd.Series(idades)

# Indexação posicional
series_idades[0]        # Primeiro elemento
series_idades[-1]       # Último elemento

# Ordenação de dados
series_idades = series_idades.sort_values()

# Diferença entre [] e .iloc[]
series_idades[0]        # Pode mudar após ordenação!
series_idades.iloc[0]   # Sempre o primeiro por posição

# Slicing (fatiar)
series_idades.iloc[:3]    # Primeiros 3 elementos
series_idades.iloc[::-1]  # Ordem reversa

# Índices personalizados
nomes = ["Téo", "Maria", "Jose", "Luis", "Ana", ...]
series_idades = pd.Series(idades, index=nomes)
```

**Aprendizado**: Diferenças entre indexação por posição e por rótulo. Importância do `.iloc[]` após ordenação.

### 📝 `04_dataframes.py`
```python
import pandas as pd

idades = [32, 38, 30, 30, 31, 35, 25, 29, 31, 37, 27, 23, 36, 33, 39]
nomes = ["Téo", "Maria", "Jose", "Luis", "Ana", ...]

# Criando Series separadas
series_idades = pd.Series(idades)
series_nomes = pd.Series(nomes)

# Criando DataFrame
df = pd.DataFrame()
df["idades"] = series_idades
df["nomes"] = series_nomes

# Acessando dados do DataFrame
df.iloc[0]["nomes"]   # Nome da primeira pessoa
df.iloc[-1]["idades"] # Idade da última pessoa
```

**Aprendizado**: DataFrames como combinação de Series. Estrutura tabular para organizar dados relacionados.

## 🔍 Conceitos Importantes

### 🎯 Por que usar Pandas?
| **Python Puro** | **Pandas** |
|------------------|------------|
| `sum(lista) / len(lista)` | `series.mean()` |
| Loop manual para variância | `series.var()` |
| Código extenso | Código conciso |

### 📈 Métodos Estatísticos da Series
- `.mean()` - Média aritmética
- `.var()` - Variância
- `.describe()` - Resumo estatístico completo
- `.std()` - Desvio padrão
- `.min()` / `.max()` - Valores mínimo e máximo

### 🎯 Diferença Crucial: `[]` vs `.iloc[]`

| **Situação** | **`series[0]`** | **`series.iloc[0]`** |
|--------------|-----------------|---------------------|
| **Antes da ordenação** | Primeiro valor original | Primeiro valor original |
| **Após `.sort_values()`** | ⚠️ Pode ser DIFERENTE! | ✅ Sempre primeira posição |

> 💡 **Dica de Ouro**: Use sempre `.iloc[]` quando quiser acessar por posição, independente da ordenação!

### 📊 Series vs DataFrame

| **Series** | **DataFrame** |
|------------|---------------|
| 1 dimensão (coluna) | 2 dimensões (tabela) |
| `pd.Series([1,2,3])` | `pd.DataFrame({'col': [1,2,3]})` |
| Uma única sequência | Múltiplas colunas |

## 🧪 Exercícios Práticos

### ✏️ Para Fixar o Aprendizado:

1. **Crie uma Series** com as notas de um aluno: `[8.5, 9.0, 7.5, 8.0, 9.5]`
2. **Calcule a média** usando o método `.mean()`
3. **Obtenha um resumo** usando `.describe()`
4. **Compare** o resultado com cálculo manual

### 🎯 Exercícios de Indexação:

1. **Crie uma Series** com idades e ordene com `.sort_values()`
2. **Teste a diferença** entre `series[0]` e `series.iloc[0]` após ordenação
3. **Use slicing** para pegar os 3 menores valores: `.iloc[:3]`
4. **Inverta a ordem** com `.iloc[::-1]`

### 📊 Exercícios de DataFrame:

1. **Crie um DataFrame** com colunas 'nome' e 'idade'
2. **Acesse** o nome da primeira pessoa
3. **Acesse** a idade da última pessoa
4. **Adicione** uma nova coluna 'cidade'

### 🎲 Desafio Extra:
Crie um DataFrame com dados de produtos (nome, preço, categoria) e descubra:
- Qual o produto mais caro usando `.iloc[]`?
- Como acessar todos os preços de uma vez?
- Como criar um resumo estatístico dos preços?

## 💡 Dicas Importantes

> ⚠️ **Lembre-se**: Series são como listas do Python, mas com "superpoderes" estatísticos!

> 💡 **Dica**: Use sempre `.describe()` para ter uma visão geral rápida dos seus dados

> 🎯 **Fundamental**: Entenda a diferença entre `[]` e `.iloc[]` - isso evitará muitos bugs!

> 📊 **Conceito-chave**: DataFrames = múltiplas Series organizadas em colunas

> 🚀 **Próximo passo**: No Dia 2 vamos aprender a importar dados de arquivos CSV!

## 🏆 Conquistas Desbloqueadas

- ✅ **Primeiro pandas**: Criou sua primeira Series
- ✅ **Estatístico ninja**: Descobriu os métodos estatísticos automáticos  
- ✅ **Indexador expert**: Dominou `.iloc[]` e indexação posicional
- ✅ **Organizador de dados**: Criou seu primeiro DataFrame
- ✅ **Slicing master**: Aprendeu a fatiar dados como um profissional

---

## 📚 Referências Úteis

- 📖 [Documentação oficial do Pandas](https://pandas.pydata.org/docs/)
- 🎥 [Vídeo da aula](https://youtube.com/@teomewhy)
- 📊 [10 minutos para pandas](https://pandas.pydata.org/docs/user_guide/10min.html)

---

<div align="center">

**🎉 Parabéns! Você deu o primeiro passo no mundo da análise de dados!**

*Continue praticando e experimentando com diferentes dados* 💪

</div>