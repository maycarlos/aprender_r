# Aprender R (Swirl stats)

## Lesson 1

- Simples adições resultam sempre num output na consola.  
- Qualquer tipo de atribuição de valor não mostra qualquer tipo de output.  
- Operações básicas -> (+, - , * , / , ^, sqrt(), etc.).  
- Criação de vetores -> c() .
- Podemos considerar números isolados como 100, vetores com length = 1.  
- Ao adicionar vetores com tamanhos diferentes(mas que o vetor maior seja divisível pelo mais pequeno) ,o R 'recicla' estes constituintes.  
- Por exemplo -> c(1,2,3,4) + 10 = c(1,2,3,4) + c(10,10,10,10).  
- Caso não seja divisível a operação érealizada na mesma mas a consola irá avisar que o resultado poderá ser estranho.  

## Lesson 2  

- Obter a pasta onde se está a trabalhar -> getwd().  
- A lista de todos os objetos dentro do workspace local -> ls().  
- Lista de todos os ficheiros dentro de uma lista -> list.files().  
- Para obter os argumentos necessarios para uma determinada funçao -> args().  
- Criar uma pasta -> dir.create().  
- Mudar de pasta de trabalho -> setwd().  
- Criar um ficheiro -> file.create().  
- Verificar se um certo ficheiro existe -> file.exists().  
- Ver informação sobre um certo ficheiro -> file.info().  
- Mudar o nome de um certo ficheiro -> file.rename(antes, depois).  
- Apagar ficheiro da pasta de trabalho -> file.remove().
- Fazer uma cópia de um certo ficheiro -> file.copy().  
- Ver o path relativo de um ficheiro -> file.path().  
