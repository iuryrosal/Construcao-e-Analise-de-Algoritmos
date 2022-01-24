# Estrutura de Dados - Listas Duplamente Encadeadas
![](https:#badgen.net/badge/nivel/★/green?)

## Tutorial (PT-BR)
[![Listas Duplamente Encadeadas](http://img.youtube.com/vi/UFuqP40byj8/0.jpg)](http://www.youtube.com/watch?v=UFuqP40byj8 "Listas Duplamente Encadeadas | Estrutura de Dados")

## Teoria

### Buscar
```python
BUSCAR(L, k) 
  x ← L.inicio # coleta primeiro objeto da lista
  Enquanto x ≠ NULO e x.chave ≠ k Faça # verifica se a chave do objeto x é diferente de k
    x ← x.proximo # Avança para o próximo objeto
  Retorna x # Se encontrar alguma coisa, retornará o objeto x onde está localizado k
```

### Inserir

```python
INSERIR (L, x) 
  x.prox ← L.inicio # Colocamos o elemento antes do objeto INICIO
  Se L.inicio ≠ None Então
    L.inicio.anterior ← x  # O INICIO antes da adição do objeto de chave X será declarado anterior a ele
  L.inicio ← x # INICIO definido agora para o novo elemento
  x.anterior ← None # Não existirá elemento anterior ao adicionado recentemente
```

### Remover
```python
DELETAR (L, x)
  Se x.anterior ≠ None então
    x.anterior.proximo ← x.proximo # O próprio elemento será agora o próximo dele (se referindo a extremidade direita).
Senão
  L.inicio ← x.proximo # Se estivermos se referindo a um termo que o seu anterior é nulo, então provavelmente é o inicio da lista, então o próximo dele assumirá o início da lista
Se x.proximo ≠ None Então
  x.proximo.anterior ← x.anterior # O próprio elemento será agora o anterior dele (se referindo a extremidade esquerda).
```