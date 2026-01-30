# poc-holiday-ai

Prova de Conceito (PoC) experimental em Python Notebook para otimização da programação de férias usando Programação Linear Inteira (MILP).

## 🎯 Objetivo

Otimizar a alocação de dias de férias maximizando o período contínuo de descanso, considerando:
- Dias úteis (segunda a sexta)
- Fins de semana (sábado e domingo)
- Feriados nacionais
- Feriados "imprensados" (pontes)

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
dias_solicitados = 15
resultado = otimizar_ferias(dias_solicitados)
```

## 📋 Requisitos

- Python 3.7+
- PuLP (biblioteca de modelagem MILP)
- Pandas (opcional, para manipulação de dados)
- Solver CBC (incluído automaticamente com PuLP)

## 🧠 Abordagem Técnica

O problema é modelado como um problema de Programação Linear Inteira (MILP) com:

- **Variáveis binárias**: Indicam quais dias úteis são usados como férias
- **Restrições**: 
  - Número exato de dias de férias solicitados
  - Continuidade do bloco de férias
- **Função objetivo**: Maximizar o período contínuo de descanso

## 📝 Notas

- Ano fixo: 2026
- Feriados brasileiros configurados para 2026
- Apenas um bloco contínuo de férias é considerado
- Dias de férias consomem apenas dias úteis
