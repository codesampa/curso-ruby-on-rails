# Começando em Ruby
Tenha em mente que **Ruby** é simples.<br/>
Vamos comparar um simples "Olá, mundo" entre ele e Java.

**Java**

	public class HelloWorld {
		public static void main(String args[]) { 
		  	String variavel = "Olá,  mundo";
		 	System.out.println(variavel);
	 	}
	}

**Ruby**
	
	variavel = "Olá, mundo"
	puts variavel



Para exibir uma mensagem para o usuários podemos utilizar os comandos **print** e **puts**, o comando print não tem quebra de linha e o comando puts tem a quebra de linha.
	
	print "Aqui não vai quebrar uma linha"
	print " , será que vai quebrar ?"
	puts " "
	puts "Aqui QUEBRAMOS a linha"
	puts "Tá vendo ?"

## Variáveis
Você pode criar uma variável que é um objeto localizado na memória do computador e atribuir um valor ou expressão a ele.<br/>
Exemplo de variáveis recebendo um texto em ruby

	nome = "Mariana"
	numero_casa = 374

#### Constantes
Uma constante é uma variável que nunca muda de valor podendo ser declarada com qualquer letra maíscula de A-Z.
	
	VARIAVEL = "Isso é uma constante"
	V_ARIAVEL = "Outra constante"

## Tipos de dados
Temos suporte a **Fixnums**, **Bignums**, **Floats**, **Racionais**, **Booleanos**, **Nulos**, **Strings**, **Symbol**, **Arrays** e **Hashes**.

> Os testes a seguir iremos utilizar o IRB(um interpretador interativo do ruby)<br/>
> Abra seu terminal e rode o comando **irb** e para sair utilize o comando **exit**

### Fixnums
São números inteiros e podem ser declarados da seguinte maneira
	
	1234

Caso tenha um número muito grande de caracteres tente colocar o sinal de _ para facilitar a leitura deles

	1_024

### Bignums
São números inteiros que suportam uma quantidade de caracteres maior que os fixnums

	900000000000000000.class
	=> Fixnum
	irb(main):004:0> 9000000000000000000000.class
	=> Bignum

### Floats
O senhor tem R$25,50 ? basta colocar um ponto "."

	25.50.class
	=> Float

### Racionais
Um número racional é aquele que pode ser representado por uma razão ou fração, por exemplo um terço seria 1 sobre 3

	irb(main):009:0> Rational(1,3)*9
	=> (3/1)
	irb(main):010:0> Rational(1,3)
	=> (1/3)
	irb(main):011:0> Rational(1,3).to_s
	=> "1/3"

### Booleanos
São números verdadeiros e falsos, podendo ser declarados como true e respectivamente false

	irb(main):014:0> verdadeiro = true
	=> true
	irb(main):015:0> falso = false
	=> false

### Nulos
Nulos são definidos como nil, e podemos perguntar se uma variável é nula utilizando a função .nil?

	irb(main):016:0> numero = 1
	=> 1
	irb(main):017:0> numero.nil?
	=> false
	irb(main):018:0> numero = nil
	=> nil
	irb(main):019:0> numero.nil?
	=> true

### Strings
São conjuntos de caracteres, que podem ser criados utilizando "aspas duplas" ou 'aspas simples'

	variavel1 = 'utilizando aspas simples'
	viariavel2 = "utilizando aspas duplas"

Podemos juntar strings

	irb(main):024:0> nome = "Henrique"
	=> "Henrique"
	irb(main):025:0> sobrenome = "Breim"
	=> "Breim"
	irb(main):026:0> nome + " " + sobrenome
	=> "Henrique Breim"

### Arrays
Definindo o array em uma simples frase para não complicar "É uma variável com diversas casas, que podem ser acessadas" ( na verdade ele é um vetor ) .

	irb(main):028:0> variavel = ["Paulo", "Maria", 1]
	=> ["Paulo", "Maria", 1]
	irb(main):029:0> variavel[0]
	=> "Paulo"
	irb(main):030:0> variavel[2]
	=> 1
	irb(main):031:0> variavel.first
	=> "Paulo"
	irb(main):032:0> variavel.last
	=> 1
	irb(main):033:0>
	
### Symbols
Símbolos, são instâncias da classe Symbol. Devemos pensar em Symbols como o seu significado e não o seu valor ou conteúdo.
Podemos declarar symbols da maneira a seguir: **:nome**, **:rua**, **:cidade**

### Hashes
Hashes são arrays indexados, podendo ser acessados através de chaves e valores
	
	dados = {cidade: 'São Paulo', fundacao: { dia: 22, mes: 01, ano: 1554 } }
	
Para acessar os dados podemos fazer a chamada da seguinte maneira

	irb(main):018 > dados[:cidade]
 	=> "São Paulo" 
 	
Para pegar o ano da fundação podemos avançar dentro de outro hash que está contido dentro do valor "fundacao"

	head :019 > dados[:fundacao][:dia]
	 => 22 
	head :020 > dados[:fundacao][:ano]
	 => 1554 

## Operadores aritméticos

Operador  | Função
------------- | -------------
+ | Adição
- | Subtração
* | Multiplicação
/ | Divisão
% | Módulo
** | Exponente


Exemplos

	irb(main):033:0> 10+10
	=> 20
	irb(main):034:0> 50-10
	=> 40
	irb(main):035:0> 25/5
	=> 5
	irb(main):036:0> 5*10
	=> 50
	irb(main):037:0> 10%20
	=> 10
	irb(main):038:0> 10**20
	=> 100000000000000000000
	irb(main):039:0> 

## Operadores de comparação

Operador  | Função
------------- | -------------
**==** | Checa se o valor corresponde ao mesmo valor comparado(verifica se é idêntico), retornando true ou false
**!=** | Checa se os valores são diferentes, retornando true ou false
**>** | Verifica se o valor é maior que (se o valor da esquerda é maior que o da direita), retornando true ou false
**<** | Verifica se o valor é menor que (se o valor da esquerda é menor que o da direita), retornando true ou false
**>=** | Verifica se o valor é menor que (se o valor da esquerda é menor que o da direita), retornando true ou false
**<=** | Verifica se o valor é menor ou igual, retornando true ou false
**<=>** | Operador de combinação. Retorna 0 se o primeiro operador for igual o segundo, 1 se o primeiro operador for maior que o segundo e -1 se o primeiro operador for menor que o segundo
**===** | Verifica se o objeto tem o mesmo valor e tipo de dados, retornando true ou false
**.eql?** |  A mesma coisa que o item anterior
**.equal?** | Retorna verdadeiro se o Objeto tiver o mesmo .object_id

Exemplos

	2.2.2 (main)> 10 == 10
	=> true
	2.2.2 (main)> 10 != 10
	=> false
	2.2.2 (main)> 10> 100
	=> false
	2.2.2 (main)> 10 < 100
	=> true
	2.2.2 (main)> 10 > 10
	=> false
	2.2.2 (main)> 10 >= 10
	=> true
	2.2.2 (main)> 10 <= 10
	=> true
	2.2.2 (main)> 50 <=> 50
	=> 0
	2.2.2 (main)> 50 === 50
	=> true
	2.2.2 (main)> 50.eql?(50)
	=> true
	2.2.2 (main)> 50.eql?(50.0)
	=> false
	2.2.2 (main)> var = 10
	=> 10
	2.2.2 (main)> var2 = 10
	=> 10
	2.2.2 (main)> var.eql?(var2)
	=> true
	2.2.2 (main)> var.object_id
	=> 21
	2.2.2 (main)> var2.object_id
	=> 21

## Operadores lógicos

Operador  | Função
------------- | -------------
**AND** | podemos ler como "E" se os dois operadores retornarem true então a condição é verdadeira
**OR** | podemos ler como OU Se qualquer um dos dois operandos são diferentes de zero, então a condição se torna verdade
**&&** | mesma coisa do operador AND
**`||`**  | mesma coisa do Operador OR
**!**  | Comprador negativo Ex: !(10 == 11) retorna true
**not** | Mesma coisa do ponto de esclamação

> OR e AND na verdade são diferentes de || e && <br/>
> Você deve usar && e || para lógica boleana e and e or para fluxos de controle.

Exemplos

	2.2.2 (main)> a = 10
	=> 10
	2.2.2 (main)> b = 20
	=> 20
	2.2.2 (main)> (a and b) == true
	=> false
	2.2.2 (main)> (a and b) == 10
	=> false
	2.2.2 (main)> (a and b) == 20
	=> true
	2.2.2 (main)> (a or b) == 20
	=> false
	2.2.2 (main)> (a or b) == 10
	=> true
	2.2.2 (main)> (a && b) == 20
	=> true
	2.2.2 (main)> (a && b) == 10
	=> false
	2.2.2 (main)> (a || b) == 20
	=> false
	2.2.2 (main)> (a || b) == 10
	=> true
	2.2.2 (main)> !(a && 5)
	=> false
	2.2.2 (main)> not(a && b)
	=> false
[Fonte em inglês](http://www.tutorialspoint.com/ruby/ruby_operators.htm)

### Executando nossos programas
Para executar um promagrama em ruby basta salvar o seu código com a extensão .rb<br/>
Exemplo

	puts "Essa é a mensagem a ser exibida"
	
Salve o arquivo como **hello.rb**	 e execute o mesmo rodando na pasta onde está o arquivo 
	
	ruby hello.rb
	
O resultado exibido na tela será:
	
	Essa é a mensagem a ser exibida
 
> O comando deve ser executado na mesma pasta onde o arquivo foi salvo, para isso rode o comando `ls` no terminal para ver se o arquivo está presente no mesmo diretório
