# Aprender R

## [Swirl Stats](https://swirlstats.com/)

## Lesson 1 - *Basic Building Blocks*

- Simples adições/operações resultam sempre num output na consola.  
- Qualquer tipo de atribuição de valor não mostra qualquer tipo de output.  
- Operações básicas -> (+, - , * , / , ^, sqrt(), etc.).  
- Criação de vetores -> c().
- Podemos considerar números isolados como 100, vetores com length = 1.  
- Ao adicionar vetores com tamanhos diferentes(mas que o vetor maior seja divisível pelo mais pequeno), o R 'recicla' estes constituintes.  
- Por exemplo -> c(1,2,3,4) + 10 = c(1,2,3,4) + c(10,10,10,10).  
- Caso não seja divisível a operação érealizada na mesma mas a consola irá avisar que o resultado poderá ser estranho.  

## Lesson 2 -  *Workspace and Files*

- Obter a pasta onde se está a trabalhar -> getwd().  
- A lista de todos os objetos dentro do workspace local -> ls().  
- Lista de todos os ficheiros dentro de uma lista -> list.files().  
- Para obter os argumentos necessarios para uma determinada funçao -> args().  
- Criar uma pasta -> dir.create().  
- Mudar de pasta de trabalho -> setwd().  
- Criar um ficheiro -> file.create().  
- Verificar se um certo ficheiro existe -> file.exists().  
- Ver informação sobre um certo ficheiro -> file.info().  
- Mudar o nome de um certo ficheiro -> file.rename(antes,  depois).  
- Apagar ficheiro da pasta de trabalho -> file.remove().
- Fazer uma cópia de um certo ficheiro -> file.copy().  
- Ver o path relativo de um ficheiro -> file.path().  

## Lesson 3 - *Sequence of Numbers*

- Forma mais simples de fazer uma sequência é assim -> 1:20 (dá todos os números inteiros de 1 até 20)
- Também se pode fazer uma sequência desta forma -> seq()
- Mas enquanto que uma sequência criada com o operador ":" dá sempre numa sequência de número em incrementos = 1, com a  função seq() nós podemos alterar este incremento utilizando o argumento -> by= x.  
- Também se nos interessar podemos gerar uma sequência com uma certa quantidade específica de números utilizando o argumento -> length= x.  
- Se por ventura não sabermos o tamanho da sequência que estamos a trabalhar, uma maneira de se saber é combinando o operador ":" com a função lenght() assim -> 1:length(my_seq).  
A outra forma de se ver o tamanho da sequência é usar o comando -> seq(along.with = my_seq).
- Mas o R já tem uma função para desempenhar este tipo de tarefa -> seq_along().  
- Mais uma forma de criar sequências de números -> rep( x, times = n, each = m).  
times (vezes que queremos que se repita).  
each (quantas vezes queremos que cada elemento se repita).  

## Lesson 4 - *Vectors*

- Vetores são a data structure mais simples  e comum em R.  
- Existem dois tipos de vetores: atomic vectors e lists.  
- Atomic vectors contem apenas um tipo de dado enquanto que uma lista podes conter vários tipos de dados.  
Vamos primeiro explorar atomic vectores e depois passamos para listas.  
- Nas lições anteriores lidamos apenas com vetores numericos que são um tipo de atomic vector.  
Outros tipos de atomic vectors incluem: logical, character, integer e complexos.  
Nesta lição vamos focar nos logical e character vectors.

### 4.1 - *Logical Vectors*  

- Vetores logicos contêm os valores *TRUE*, *FALSE* e *NA* (de 'not available').  
Este valores são gerados a partir de logical conditions.
- Uma expressão do género tf = c(0.5,55,-10, 6) < 1 diz-nos se cada integrante deste vetor é menor que 1 usando *TRUE* ou *FALSE* e cria um vetor com estes valores.  
- Os símbolos '**<**' , '**<=**' , '**>=**' , '**>**' , '**=**' , '**!=**' são demominados logical operators.
- Quando temos duas logical expressions **A** e **B**, podemos perguntar se pelo menos uma é *TRUE* com  **A | B** (operador para 'ou' e também 'união').  
Para se verificar se a duas são *TRUE* utiliza-se a **A & B** (operador para 'e' e também 'intersecção').  
Por fim, **!A** é a negação de A que é *TRUE* quando **A** é *FALSE* e vice-versa.  

### 4.2 - *Character Vectors*  

- Character vectors também são muito utilizados em R e são distinguidos pelos outros tipos através do uso de aspas para os seus elementos.  
- Se quisermos juntar todos os contituintes do vetor de tamamho 3 que temos e torna-lo num vetor de tamanho 1 podemos usar uma funcão denominada -> paste(x , collaplse = ' ').  
 O parametro colapse diz a função o que deve meter entre os elementos do vetor x.  
- Para adicionar algum elemento a um certo vetor pode-se usar a função c assim -> c(x, y), onde x é o vetor que já tinhamos e o y é o elemento que desejamos adicionar.  
