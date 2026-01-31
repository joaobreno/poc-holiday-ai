# poc-holiday-ai

Prova de Conceito (PoC) experimental em Python Notebook para otimização da programação de férias usando Programação Linear Inteira (MILP).

## 🎯 Objetivo

**Input:** Número de dias corridos de férias desejados (ex: "Quero 10 dias de férias")

**Output:** Encontrar a janela de 10 dias corridos que **maximiza** o período total de folga, aproveitando fins de semana e feriados adjacentes.

### Exemplo

- Input: 10 dias corridos de férias
- Janela selecionada: 18/fev a 27/fev (10 dias corridos)
- **Aproveita antes:** 14-15/fev (fim de semana) + 16-17/fev (Carnaval) = 4 dias bônus
- **Período TOTAL de folga:** 14/fev a 27/fev = **14 dias totais!**
- **Resultado:** Você tira 10 dias corridos e folga 14 dias consecutivos!

### Como funciona

1. Você escolhe quantos dias corridos quer tirar de férias (ex: 10 dias)
2. O modelo encontra a melhor janela de 10 dias no calendário
3. Expande para trás e para frente aproveitando fins de semana e feriados adjacentes
4. **Você folga mais dias do que tirou!**

## 🚀 Instalação

1. Clone o repositório ou baixe os arquivos
2. Instale as dependências:

```bash
pip install -r requirements.txt
```

## 📓 Uso

1. Abra o notebook `holiday_optimization.ipynb` no Jupyter Notebook ou JupyterLab
2. Execute todas as células em ordem
3. Na célula de interface do usuário, altere o valor de `dias_solicitados` conforme necessário

Exemplo:
```python
# Quero 10 dias CORRIDOS de férias
dias_corridos = 10
resultado = otimizar_ferias(dias_corridos)
```

## 📋 Requisitos

- Python 3.7+
- PuLP (biblioteca de modelagem MILP)
- Pandas (opcional, para manipulação de dados)
- Solver CBC (incluído automaticamente com PuLP)

## 🧠 Abordagem Técnica

O problema é modelado como um problema de Programação Linear Inteira (MILP) com:

- **Variáveis binárias**: Indicam qual janela de N dias corridos é selecionada
- **Pré-cálculo**: Para cada janela possível de N dias corridos:
  1. Calcula quantos dias úteis ela consome
  2. Expande para trás e para frente incluindo fins de semana/feriados adjacentes
  3. Calcula o período TOTAL de folga resultante
- **Restrições**: 
  - Apenas uma janela de N dias corridos selecionada
  - Janela contínua de dias
- **Função objetivo**: **MAXIMIZAR** o período total de folga (janela + adjacentes)

## 📝 Notas

- Ano fixo: 2026
- Feriados brasileiros configurados para 2026
- Período contínuo de N dias corridos solicitados
- Otimização: **maximizar período total de folga** aproveitando fins de semana e feriados adjacentes
- O modelo garante que você folga mais dias do que solicitou!

## 💡 Por que isso é útil?

Em vez de escolher aleatoriamente quando tirar férias, o modelo encontra automaticamente:
- O melhor período do ano para suas férias
- Aproveita feriados próximos (como Carnaval, Páscoa, etc.)
- Aproveita fins de semana adjacentes
- **Maximiza seu descanso com o mesmo número de dias de férias!**
