# Estruturas de controle

São estruturas que permitem controlar a ordem na qual as instruções, expressões e chamadas de funções são executadas em nosso programa.


### IF
Interprete o **IF** em português como se fosse "SE" e o **ELSE** como se fosse "SE NÃO", logo podemos ler SE o nome é pedro exiba a frase que o nome está correto, se não exiba que o nome não está correto.

	nome = "Pedro"
	if nome == "Pedro"
	  puts "O nome está correto"
	else
	  puts "O nome não está correto"
	end

> Lembre-se toda estrutura de controle em ruby termina com `end`

Podemos receber uma variável utilizando a função gets e a função .chomp para formatar o valor recebido para string

	print "Digite um valor :"
	nome = gets.chomp
	
	if nome == "Pedro"
	  puts "O nome está correto"
	else
	  puts "O nome não está correto"
	end
	


### ELSIF
Interprete o **ELSIF** como MAIS SE ou seja mais se o valor for "pedro" ele entra dentro desta chamada e executa a frase.

	print "Digite um valor :"
	nome = gets.chomp
	
	if nome == "Pedro"
	  puts "O nome está correto"
	elsif nome == "pedro"
	  puts "O nome está correto, mas em letra minúscula"
	else
	  puts "O nome não está correto"
	end


### Unless
Ao contrário do **IF** que verifica se a expressão é **verdadeira**, o **unless** verifica se a expressão é **falsa** para entrar na condição como o exemplo abaixo. 

	valor = 10
	unless valor == 10
	  puts "O valor não é 10, mas se tivessemos colocado if o programa iria rodar aqui"
	else
	  puts "O valor inserido é 10, mas como usamos o unless acabou aqui o programa"
	end

No caso acima o nosso programa irá exibir a seguinte frase:
`O valor inserido é 10, mas como usamos o unless acabou aqui o programa`

### Case
Bem parecido com o **IF**, mas ele pode comparar expressões também

	valor = 10
	case i 
	when 0..5
	    puts "entre 0 e 5"
	when 6..10
	  puts "entre 6 e 10" 
	else
	    puts "Não corresponde a nenhum valor"
	end

Também podemos usar strings
	
	nome = "Paulo"
	case nome
	when "Paulo"
	    puts "Achamos o Paulo"
	when "Maria"
	  puts "Achamos a Maria"
	else
	    puts "Não achamos ninguém"
	end

A saída acima foi:

	Achamos o Paulo
	
### Loops
Loop é algo que fica se repetindo até a condição chegar onde foi programada, podemos interagir dentro do loop com as seguintes maneiras.<br/>
Temos em ruby disponível **while**(faça enquanto), **for**(para essa condição em) e **until**(faça até que).

- **break** - sai do loop
- **next** - vai para a próxima iteração
- **return** - sai do loop e do método onde o loop está contido
- **redo** - repete o loop do início, sem reavaliar a condição ou pegar o próximo elemento

### While
**Faça até que**... enquanto a condição for **verdadeira** ou seja chega ao valor 10 como em nosso exemplo abaixo.<br/>

	i=0
	while i < 10
	  puts i
	  i += 1
	end
	
>  Em C utilizamos ++ e -- em ruby usamos += e -= acréscimo e decréscimo.

> Lembre-se em computação contamos o número 0, neste caso ele irá exibir até o número 9 caso deseje contar até 10 utilize o operador

Exemplo de uma tabuada utilizando o while

	print "Insira um número para fazermos a tabuada: "
	numero = gets.to_i
	i=1
	while i <= 10
	  puts "#{numero} vezes #{i} é #{i*numero}"
	  i += 1
	end


Também podemos fazer arrays utilizando o atalho **%w** e percorre-lo utilizando o while sendo passado a posição com o valor de **i**

	nomes = %w(Paula Partricia Bruna Juliana)
	i=0
	while i < 4
	  puts "O nome é #{nomes[i]}"
	  i += 1
	end
	
### For
Para determinada condição faça<br/>
O **for** em C funciona da seguinte maneira for (**inicialização**, **condição**, **incremento**) em ruby isso fica mais simples veja o exemplo

	for i in 0..5
	  puts "O valor exibido é #{i}"
	end

O mesmo exemplo da tabuada agora sendo usado com o for

	print 'Insira um numero para nossa tabuada: '
	numero = gets.to_i
	for i in 1..10
	  puts "#{i} vezes #{numero} é #{numero*i}"
	end

Agora vamos listar alguns exemplos utilizando **break**, **next**, **return** e **redo**.

##### Break
	
	for i in(0..5)
	  break if i==2
	  puts i
	end

O resultado foi

	0
	1
##### Next

	for i in(0..5)
	  next if i==2
	  puts i
	end
	
O resultado foi

	0
	1
	3
	4
	5

##### Return

	for i in(0..5)
	  return if i==2 # vai sair e parar o programa pois não temos mais nada a executar
	  puts i
	end
	
O resultado foi

	0
	1
	return.rb:2:in `block in <main>': unexpected return (LocalJumpError)
		from return.rb:1:in `each'
		from returnrb:1:in `<main>'

##### Redo

	for i in(0..5)
	  redo if i==2
	  puts i
	end

Pare o programa agora pressionando **CTRL+C** no terminal se não vai ficar tentando rodar a condição novamente, pois ele tentou avançar para o próximo elemento mas ele está com o valor total que entra dentro da sua própria expressão então temos que para o programa.

### Until
Faça até que

	i=0
	until i==5
	  puts i
	  i +=1
	end

### Iteradores
Um interador percorre uma determinada coleção, vejamos esses exemplos

	[1,2,3,4,5].each {|e| puts "o array contem o numero #{e}"}

	10.times {puts "Ola"}
	
	(1..10).step(2).each { |e| puts "numero:  #{e}" }

Um exemplo percorrendo um array

	palavras = %w(Vamos exibir essa frase)
	for palavra in palavras
	    puts palavra
	end


## Desafios
1. Faça um sistema de conversão de Celsius para Fahrenheit e exiba o valor na tela. 
2. Dado um número exiba ele em ordem decrescente até chegar a 0
3. Percorra uma lista de arrays que seja uma frase utilizando while, e coloque cada palavra em letra maiúscula
4. Faça uma tabuada utilizando a o iterador .times