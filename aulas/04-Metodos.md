# Métodos

São funções onde sub-rotinas que executam uma tarefa particular. Um dos grandes benefícios é não precisar copiar o código todas as vezes que precisar executar aquela operação, além de deixar a leitura do código mais intuitiva.

Um exemplo

	def ola
	  puts "Olá mundo"
	end
	
Se chamarmos o método que foi criado em nosso código ele irá executar o conteúdo dentro dele

	2.2.2 (main)> def ola
	2.2.2 (main)>   puts "Olá, mundo"
	2.2.2 (main)> end  
	=> :ola
	2.2.2 (main)> ola
	Olá, mundo
	=> nil

Imagina que diversas vezes temos que fazer uma soma em nosso código, seria mais fácil criar um método e indicar os respectivos valores

	def soma(valor1, valor2)
	  puts valor1+valor2
	end
	
Agora na prática

	def soma(valor1, valor2)
	  valor1+valor2
	end
	
	print "Entre com o primeiro valor: "
	valor1 = gets.to_i
	print "Entre com o segundo valor: "
	valor2 = gets.to_i
	
	puts soma(valor1, valor2)
	
> A função gets recebe o valor que o usuário digita na tela
	
Irei informar os valores `10` e `25` e o resultado esperado na tela será `35`

	ruby soma.rb
	Entre com o primeiro valor: 10
	Entre com o segundo valor: 25
	35

## Desafios
1. Faça um método que verifica se dois números são iguais 


