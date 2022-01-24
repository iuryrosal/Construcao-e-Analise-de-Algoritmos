# Estrutura de Dados - Filas
![](https://badgen.net/badge/nivel/★/green?)

## Tutorial (PT-BR)
<Em construção>

## Teoria

### Percurso em Ordem

```python
PercursoEmOrdem(x):
|  Se x ≠ None então
|  PercursoEmOrdem(x.esq)
|  print(x) 
|  PercursoEmOrdem(x.dir)
```

### Buscar com recursividade
```python
BUSCAR(x, k):
|  Se x = None ou x.chave = 𝑘 então
|  |  Retorna 𝑥
|  Se 𝑘 < x.chave então
|  |  Retorna BUSCAR[x.esq, 𝑘]
|  Senão
|  |  Retorna BUSCAR[x.dir, 𝑘]
```

### Busca sem recursividade
```python
BUSCAR(x, k): 
|  Enquanto 𝑥 ≠ None e x.chave ≠ 𝑘 então 
|  |  Se 𝑘 < 𝐶𝐻𝐴𝑉𝐸[𝑥] então
|  |  |  x ← x.esq
|  |  Senão
|  |  |  x ← x.dir
|  Retorna x
```

### Mínimo
```python
MINIMO(x):
|  Enquanto x.esq ≠ None então #  x está em uma folha?
|  |  𝑥 ← x.esq
|  Retorna 𝑥 
# Quando x for uma folha, retornará a sua posição (nó), pois será o valor da esquerda mais extremo, logo o menor de todos.
```

### Máximo
```python
MAXIMO(x):
|  Enquanto x.dir ≠ None então # x está em uma folha ?
|  |  x ← x.dir 
|  Retorna 𝑥 
# Quando x for uma folha, retornará a sua posição (nó), pois será o valor da direita mais extremo, logo o maior de todos
```

### Sucessor
```python
SUCESSOR(x):
|  Se x.dir ≠ None então # se possui direita (que possui números maiores que x.chave)
|  |  Retorna MÍNIMO[x.dir] # busca o lado "mais esquerdo" onde possui o menor dos maiores valores de x.chave.
|  𝑦 ← x.pai
|  Enquanto 𝑥 ≠ None e 𝑥 = y.dir faça # x é filho da direita de y?
|  |  𝑥 ← 𝑦 # x sobe um nível
|  |  𝑦 ← y.pai # y sobe um nível
|  Retorna y 
# y foi deslocado para a direita e x passa a ser seu filho da esquerda
```

### Incluir
```python
INCLUIR(T, z):
|  y ← None
|  x ← T.raiz
|  Enquanto 𝑥 ≠ None faça 
|  # percorre a árvore até encontrar o local ideal do elemento
|  |  y ← x # coleta informação do pai de x
|  |  Se z.chave ≤ x.chave então
|  |    x ← x.esq
|  |  Senão
|  |    x ← x.dir
|  z.pai ← y 
|  # pai do novo elemento estará no local do y
|  Se y = None então # identifica que a árvore está vazia
|  |  T.raiz ← z 
|  Senão se z.chave < y.chave então # insere o elemento no local ideal
|  |  y.esq ← z
|  Senão
|  |  y.dir ← z
|  z.esq ← None
|  z.dir ← None
```
### Transplantar
```python
TRANSPLANTAR(T, u, v):
|  Se u = T.raiz então 
|  # Verifica se u foi posicionado no lugar da raiz da árvore binária T
|  |  T.raiz ← v # v se torna raiz da árvore
|  Senão se u = u.pai.esq então 
|  # Verifica se u está no lado esquerdo da árvore
|  |  u.pai.dir ← v
|  Senão
|  |  u.pai.dir ← v
|  Se 𝑣 ≠ None então
|  |  v.pai ← u.pai
```

### Remover
```python
REMOVER(T, z):
|  Se z.esq = None então
|  |  TRANSPLANTAR(𝑇, z, z.dir)
|  Senão se z.dir = None então
|  |  TRANSPLANTAR(𝑇, z, z.esq)
|  Senão
|  |  y ← MINIMO(z.dir)
|  Se y.pai ≠ z então
|  |  TRANSPLANTAR(𝑇, y, y.esq)
|  |  y.dir ← z.dir
|  |  y.dir.pai ← y
|  y.esq ← z.esq
|  y.esq.pai ← y
```