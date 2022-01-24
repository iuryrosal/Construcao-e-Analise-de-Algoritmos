# Estrutura de Dados - Filas
![](https://badgen.net/badge/nivel/★/green?)

## Tutorial (PT-BR)
[![Filas](http://img.youtube.com/vi/3_lKo9TMewg/0.jpg)](http://www.youtube.com/watch?v=3_lKo9TMewg "Filas | Estrutura de Dados")

## Teoria

### Inserir

```python
ENQUEUE(S, x)
Q[Q.fim] ← x # O elemento será inserido na posição após o último elemento da fila
Se Q.fim = Q.comprimento então
  Q.fim ← 1  # A posição irá voltar para a primeira posição da fila
Senão
  Q.fim ← Q.fim + 1 # Se possível, ele avança posição FIM para a próxima operação
```

### Remover
```python
DEQUEUE(S)
x ← Q[Q.inicio] # O nó do começo da fila será selecionado
Se Q.inicio = Q.comprimento então
  Q.inicio ← 1 #Caso tenha chegado ao final da fila, voltará para o começo
Senão
  Q.inicio ← Q.inicio + 1 # Avança uma posição para pegar o novo começo da fila
  Retorna x #Mostra nó removido
```