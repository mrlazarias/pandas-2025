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

## 🧪 Exercícios Práticos

### ✏️ Para Fixar o Aprendizado:

1. **Crie uma Series** com as notas de um aluno: `[8.5, 9.0, 7.5, 8.0, 9.5]`
2. **Calcule a média** usando o método `.mean()`
3. **Obtenha um resumo** usando `.describe()`
4. **Compare** o resultado com cálculo manual

### 🎲 Desafio Extra:
Crie uma Series com os preços de produtos e descubra:
- Qual o produto mais caro?
- Qual a média de preços?
- Quantos produtos custam acima da média?

## 💡 Dicas Importantes

> ⚠️ **Lembre-se**: Series são como listas do Python, mas com "superpoderes" estatísticos!

> 💡 **Dica**: Use sempre `.describe()` para ter uma visão geral rápida dos seus dados

> 🚀 **Próximo passo**: No Dia 2 vamos aprender a importar dados de arquivos CSV!

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