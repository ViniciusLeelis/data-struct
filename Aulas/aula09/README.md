# Aula - 13/09/2017

# Fila

* Filas com arrays:
    * São estruturas fixas;
    * FIFO;
    * Seu problema é ter o tamanho fixo

* Filas com listas encadeadas:
    * Sâo estruturas dinâmicas;
    * Seu problema é a complexidade.

# Pilhas

* Consigo verificar padrões 
* Tem por padrão o LIFO

# Busca em vetor ordenado

Realiza a busca de um dado valor X em um vetor V.

Há duas formas de fazer esse processo:
   * Busca sequêncial:
     * No pior caso serão dados N passos  
     * Busca demorada;
     * Não leva em conta a estrutura dos dados;
     * Passa elemento a elemento do vetor
    * Busca binária:
     * Rápida;
     * Leva em consideração a estrutura dos dados;
     * No caso de um valor 2 ^ 1000000
        * O algoritimo leva apenas 13 passos, isso porque trabalha dividindo cada passo em 2

# Algoritimos de busca


* Algoritimos bons:
    * Algoritimos bons utilizam, n * log(base 2) n, isso porque a cada divisão (por 2), terei o log(base 2) de n.  

* Algoritimos ruins:
    * Algoritimos ruins acabam trabalhando com N ^ 2, onde N é o tamanho do vetor, assim a busca passa duas vezes, pelo mesmo elemento.
    * 1° Exemplo de um algoritimo ruim de ordenação (Inserção):
        <code> 
   
                 1° Passo: 0, 3, 6, 1, 5, 4, 2, 7
                 2° Passo: 0, 1, 3, 6
                 3° Passo: 0, 1, 3, 5, 6
                 4° Passo: 0, 1, 3, 4, 5, 6
                 5° Passo: 0, 1, 3, 4, 5, 6, 7
                 
        </code>
        * Algoritimo ruim pois tem de passar por todos os elementos várias vezes para funcionar
    * Abaixo mais um exemplo:
        <code>
   
                1° Passo: 6, 3, 4, 5, 1, 0, 7, 2
                2° Passo: 3, 6
                3° Passo: 3, 4, 5
                4° Passo: 3, 4, 5, 6
                5° Passo: 1, 3, 4, 5, 6
                6° Passo: 0, 1, 3, 4, 5, 6
                7° Passo: 0, 2, 1, 3, 4, 5, 6
                8° Passo: 0, 2, 1, 3, 4, 5, 6, 7
        </code>
    * 2° Exemplo de algoritimo ruim de ordenação (Método de seleção):
        <code>
   
                1° Passo: 6, 3, 4, 5, 1, 0, 7, 2
                2° Passo: 0, 3, 4, 5, 1, 6, 7, 2
                3° Passo: 0, 1, 4, 5, 3, 6, 7, 2
                4° Passo: 0, 1, 2, 5, 3, 6, 7, 4
                5° Passo: 0, 1, 2, 3, 5, 6, 7, 4
                6° Passo: 0, 1, 2, 3, 4, 6, 7, 5
                7° Passo: 0, 1, 2, 3, 4, 5, 7, 6
                8° Passo: 0, 1, 2, 3, 4, 5, 6, 7
                
        </code>
        
    * Comparar os dois algoritimos. Quem é o pior ?
        * R: O de seleção, isso porque ele não leva em consideração o lado esquedo (Já ordenado), apenas o lado direito, e o algoritmo de inserção, considera o lado esquerdo.
    
    * Todos os algoritimos mostrados até aqui, são algoritimos n ^ 2





# Aula - 26/09/2017  // link do repositório de onde foi tirado: https://github.com/Gigers/data-struct   ----------

# Algoritimos rápidos de ordenação - Mergesort

O processo de intercalar demora N (Sendo ordem de grandeza N/2)

Este é um processo mais rápido que o processo de inserção e de comparação

* Abstração

0° - Receba o vetor
    [6, 7, 4, 0, 2, 1, 5, 3]
1° - Divide o vetor recebido na metade
    [6, 7, 4, 0]  [2, 1, 5, 3]
2° - Divide novamente os campos gerados na divisão anterior
    [6, 7] [4, 0] [2, 1] [5, 3]
3° - Divide novamente os campos gerados na divisão anterior
    [6] [7] [4] [0] [2] [1] [5] [3]
4° - Junta em pares de dois sorteando os menores
    [6,7] [0, 4] [1,2] [3,5]
5° - 0, 4 ,6 , 7



6,3,0,7,5,1, 2, 4


# Considerações que caem na prova

A - origem
B - Destino

Este algoritimo é bom porém consome o dobro de memória


Para um programa ser bom deve se levar em consideração dois tópicos:

* Quantidade de passos feitas pelo programa
* Espaço de memória utilizado

* Considerações sobre o algoritimo Mergesort
    * 1° - Muito mais rápido que os algoritimos de inserção e seleção (N/log(n) < n ^ 2)
    * 2° - Ocupa o dobro do espaço;
    * 3° - As metades são independentes, posso fazer em paralelo (Com threads, multiplos processadores)

# Heapsort

log(n) / 2 

# Quicksort

Se este processo for feito recursivo, no final hávera o dobro de elementos no vetor

1 2 (2 ^ 2) (2 ^ 4) (2 ^ 8)  (2 ^ 16) == log/2(n)

Aqui não há vetores auxiliares

* Considerações importantes

    * 1° - Se o vetor estiver ordenado, quicksort demora n ^ 2 passos
        * Exemplo de um passo: [0, 1, 2, 3, 4]; pivô = 0
        <code>
            menores = [] 
            maiores = [1,2,3,4]
        </code>
        * Este é o pior caso, onde todos os elementos ficam do mesmo lado
    * 2° - No entanto o Quicksort é muito rápido. Ninguém ordena um vetor ordenado
    * No pior caso n ^ 2, na media log/2(n)

# Conteúdo da prova

* Ordenar por mergesort sem ver o código
* Heapsort não cai na prova
* Quicksort
* Explicar os conceitos do quicksort
