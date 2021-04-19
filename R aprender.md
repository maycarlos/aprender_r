# Aprender R

## [Swirl Stats](https://swirlstats.com/)

## Lesson 1 - *Basic Building Blocks*

- Simples adições/operações resultam sempre num output na consola.  
- Qualquer tipo de atribuição de valor não mostra qualquer tipo de output.  
- Operações básicas -> (+, - , * , / , ^, sqrt(), etc.).  
- Criação de vetores -> c().
- Podemos considerar números isolados como 100, vetores com length = 1.  
- Ao adicionar vetores com tamanhos diferentes (mas que o vetor maior seja divisível pelo mais pequeno), o R 'recicla' estes constituintes.  
- Por exemplo -> c(1,2,3,4) + 10 = c(1,2,3,4) + c(10,10,10,10).  
- Caso não seja divisível a operação é realizada na mesma mas a consola irá avisar que o resultado poderá ser estranho.  

## Lesson 2 -  *Workspace and Files*

- Obter a pasta onde se está a trabalhar -> getwd().  
- A lista de todos os objetos dentro do workspace local -> ls().  
- Lista de todos os ficheiros dentro de uma lista -> list.files().  
- Para obter os argumentos necessários para uma determinada função -> args().  
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
- Também se nos interessar podemos gerar uma sequência com uma quantidade específica de elementos utilizando o argumento -> length= x.  
- Se por ventura, não sabermos o tamanho da sequência que estamos a trabalhar, uma maneira de se saber é combinando o operador ":" com a função lenght() assim -> 1:length(my_seq).  
A outra forma de se ver o tamanho da sequência é usar o comando -> seq(along.with = my_seq).
- Mas o R já tem uma função para desempenhar este tipo de tarefa -> seq_along().  
- Mais uma forma de criar sequências (é mais um vetor que repete o valor x, n vezes) de números -> rep( x, times = n, each = m).  
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

- Vetores lógicos contêm os valores *TRUE*, *FALSE* e *NA* (de 'not available').  
Este valores são gerados a partir de logical conditions.
- Uma expressão do género tf = c(0.5,55,-10, 6) < 1 diz-nos se cada integrante deste vetor é menor que 1 usando *TRUE* ou *FALSE* e cria um vetor com estes valores.  
- Os símbolos '**<**' , '**<=**' , '**>=**' , '**>**' , '**=**' , '**!=**' são demominados logical operators.
- Quando temos duas logical expressions **A** e **B**, podemos perguntar se pelo menos uma é *TRUE* com  **A | B** (operador para 'ou' e também 'união').  
Para se verificar se a duas são *TRUE* utiliza-se a **A & B** (operador para 'e' e também 'intersecção').  
Por fim, **!A** é a negação de A que é *TRUE* quando **A** é *FALSE* e vice-versa.  

### 4.2 - *Character Vectors*  

- Character vectors também são muito utilizados em R e são distinguidos pelos outros tipos através do uso de aspas para os seus elementos.  
- Se quisermos juntar todos os contituintes do vetor com 3 elemento que temos e torna-lo num vetor com só 1 elemento podemos usar uma funcão denominada -> paste(x , collaplse = ' ').  
 O parâmetro collapse diz a função o que deve meter entre os elementos do vetor x.  
- Para adicionar algum elemento a um certo vetor pode-se usar a função c assim -> c(x, y), onde x é o vetor que já tinhamos e o y é o elemento que desejamos adicionar.  

## Lesson 5 - *Missing Values*

- Missing values têm uma função importante em estatística e em análise de dados.  
Geralmente, estes missing values não devem ser ignorados mas sim estudados para ver se existe algum padrão ou razão que cause a existência destes tipos de valor
- Em R, **NA** é usaddo para representar qualquer valor que "não está disponível" ou que "falta".
- Qualquer operação que envolve **NA** geralmente resulta em **NA**.  
Por exemplo, se multiplicarmos o vetor c(44, NA, 5, NA) por 3 o resultado será -> (132,  NA,  15,  NA).
- rnorm(x, n)-> criar uma distribuição normal aleatória com x elementos e de média = n (default value do n é 0).
- sample(x, n) -> retira uma amostra de tamanho *n* do vetor/grupo de vetores *x*
- is.na(x) -> Verifica se os valores presentes no vetor *x* são **NA** ou não, resultando em vetores que contêm *TRUE* se o valor for **NA**  ou *FALSE* para qualquer outro tipo de dado.  
- Existe outro tipo de missing value que é o **NaN** que é denominado "not a number"

## Lesson 6 - *Subsetting Vectors*

- Nesta lição é para ver como é que se extrai elementos de um vetor em função de condições que nós delimitamos.
- Assumindo que *x* <- sample(c(rnorm(20), rep(NA, 20)), 40).  
- x[1:10] -> porção do 10 primeiros elementos do vetor *x*.
- x[is.na(x)] irá resultar num vetor com todos os elementos **NA** do vetor *x*.  
Usando o operador de negação ! podemos usar a expressão acima para obter todos os números do vetor *x* assim -> x[!is.na(x)].
- Para obtermos todos os valores que não são **NA** e são maiores do que 0 podemos usar a expressão x[!is.na(x) & x > 0]
- Se só quisermos os valores que estão na 3ª, 5ª e 7ª posição do vetor *x* usamos a expressão x(c(3,5,7)).  
Atenção que em R as posições do vetores começam a ser contadas a partir de 1.  
- Em contrapartida, se quisermos todos os elementos menos o 2º e o 10º do vetor *x* podemos utilizar a expressão x[c(-2,-10)] ou x[-c(2,10)].  

## Lesson 7 - *Matrices and Data Frames*

- Nesta lição, vão ser estudados **matrizes** e **data frames**.  
Ambos representam tipos de dados retangulares, isto significa que são utilizados para armazenar *tabular data* com linhas e colunas.
- A maior diferença entre as duas é que **matrizes** só podem armazenar um tipo de dado enquanto que **data frames** podem armazenar vários tipos de dados.
- dim() -> diz-nos as dimensões de um certo objeto.
- Podemos atribuir dimensões a um certo vetor usando a expressão dim(1:20) <- c(4,5)
- Isto fez com que o vetor passasse a ser uma **matriz** com 4 linhas e 5 colunas.  
- Outra maneira de ver as dimensões de um objeto é com a função -> attributes().  
- Para confirmar que a sequência passou a ser uma **matriz** podemos usar a função -> class() que quando é aplicada na expressão acima deverá ter o output de "matrix" "array".  
- Uma forma mais direta de criar uma **matriz** é utilizando a função -> matrix(x, i, j), sendo x o constituinte da **matriz**, i as linhas e j as colunas.
- cbind(x,y) <- combina as colunas de x com y
- Quando se faz um cbind com x e y, se x for, por exemplo, um character vector, o R irá alterar todos os contituintes da **matriz** para strings isto porque **matrizes** só aceitam um tipo de dado dentro.
- Para não termos esse tipo de problemas, usa-se **data frames** que ao contrário das **matrizes** conseguem conter diferentes tipos de dados.  
- Para atribuir nomes a colunas de uma **data frame** usa-se a seguinte expressão, colnames(x) <- values, onde x é a **data frame** e values são os nomes que queremos atribuir às colunas.

## Lesson 8 - *Logic*

- Isto vai ser uma pequena introdução a operações lógicas com R
- Temos dois valores logicos em R, **True** ou **False** e podemos construir expressões que apresentam um certo resultado se verificar uma destas duas expressões.
- Podemos usar o AND -> `&` operator para avaliar um certo valor por uma função. Esta versão do AND operator -> `&&` só avalia o primeiro valor de um vetor.  
- o OR operator segue a mesma logica. Esta versão `|` avalia com um vetor inteiro, enquanto que esta `||` só avalia o primeiro valor
