## Tutorial (PT-BR)
[![Pilhas](http://img.youtube.com/vi/TeU6ittseYs/0.jpg)](http://www.youtube.com/watch?v=TeU6ittseYs "Pilhas | Estrutura de Dados")

## Teoria

Estruturas que trabalham com o conceito de LIFO (Last In First Out), significando que "o ultimo que entra é o primeiro que sai". Esse é o melhor resumo para essa estrutura, em que podemos fazer uma analogia com uma pilha de pratos. A medida que vamos colocando os pratos, colocamos um por cima dos outros. No desejo de remover algum prato, removemos sempre o que está no topo da pilha. Dessa forma, essa estrutura funciona da mesma forma, imadinando que cada prato é uma célula que possui algo armazenado.

Para a pilha temos o seguinte atributo: 
- topo: armazena o índice do último elemento presente na pilha. Então, as operações de inserção e remoção de elementos da pilha sempre envolve esse atributo.

### Inserção de Elemento
A lógica envolve atribuir ao topo o próximo indice (topo atual + 1) e neste alocar o elemento desejado. Aqui devemos,antes de efetuar a operação, verificar se a pilha já não se encontra cheia. Caso a pilha esteja cheia (topo = n), devemos impedir que a operação ocorra, caso contrário, podemos prosseguir. Esse erro que ocorre ao inserir elemento em uma pilha cheia é denominado de **Overflow**.


### Remoção de Elemento
A lógica se resume em desalocar o elemento da estrutura. Para isso, recuamos um indice abaixo do topo (topo atual - 1). Antes de efetuar a operação, é importante verificar se a pilha está vazia (topo = 0). Caso a pilha esteja vazia, devemos impedir que a operação ocorra, caso contrário, podeos prosseguir. Esse erro que ocorre quando estamos querendo remover algum elemento de uma pilha vazia é denominado **Underflow**.

Uma coisa interessante é no caso do POP, diferente do PUSH, não precisamos informar o elemento que queremos remover, pois na pilha sempre removemos pelo topo. Uma boa prática é retornar ao usuário qual elemento foi removido.
