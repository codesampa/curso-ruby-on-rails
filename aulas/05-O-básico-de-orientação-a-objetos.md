# O básico de orientação a objetos

Em ruby tudo é um objeto, podemos exemplificar a orientação a objetos aproximando a programação do mundo real ou seja imagine que temos somos a classe Pessoa e cada pessoa tem diversos atributos tais como **nome**, **sobrenome**, **cor dos olhos** e tipo de **cabelo**.

Devemos começar criando a `class Pessoa` e depois inicializar os atributos dela com a função `def initialize` e informar os pârametros nome, sobrenome, cor_olhos e cabelo.

	class Pessoa
	  
	  def initialize(nome, sobrenome, cor_olhos, cabelo)
	    @nome = nome
	    @sobrenome = sobrenome
	    @cor_olhos = cor_olhos
	    @cabelo = cabelo
	  end
	
	  def to_s
	    "Nome:#{@nome}  Sobrenome:#{@sobrenome}  Cor dos olhos:#{@cor_olhos}  Cabelo:#{@cabelo}"
	  end
	
	end
	
	# Cria o atributo com os seus símbolos
	nova_pessoa = Pessoa.new(:nome, :sobrenome, :cor_olhos, :cabelo)
	
	# Debuga a classe e o atributo
	# p nova_pessoa
	
	puts nova_pessoa
	
	# Agora podemos passar de acordo com a posição :)
	nova_pessoa = Pessoa.new('Henrique', 'Moreno', 'Verdes', 'Careca')
	
	puts nova_pessoa
	
	
O primeiro `puts nova_pessoa` exibe a seguinte informação na tela:

`Nome:nome  Sobrenome:sobrenome  Cor dos olhos:cor_olhos  Cabelo:cabelo`

O segundo contem os valores que informamos e irá exibir a seguinte mensagem:

`Nome:Henrique  Sobrenome:Moreno  Cor dos olhos:Verdes  Cabelo:Careca`

> Note que criamos o metodo def to_s onde ele é o responsável por exebir as informações na tela

Na orientação a objetos também temos que informar quais campos o usuário pode escrever a informação e quais estão disponíveis para leitura, podemos fazer isso utilizando o método **attr_writer** para gravação e **attr_reader** para leitura conforme o exemplo abaixo:

	class Pessoa
	  attr_reader :nome, :sobrenome, :cor_olhos, :cabelo
	  attr_writer :nome
	  
	  def initialize(nome, sobrenome, cor_olhos, cabelo)
	    @nome = nome
	    @sobrenome = sobrenome
	    @cor_olhos = cor_olhos
	    @cabelo = cabelo
	  end
	
	  def to_s
	    "Nome:#{@nome}  Sobrenome:#{@sobrenome}  Cor dos olhos:#{@cor_olhos}  Cabelo:#{@cabelo}"
	  end
	
	end
	
	nova_pessoa = Pessoa.new(:nome, :sobrenome, :cor_olhos, :cabelo)
	
	# O attr_write me permite como usuário gravar uma info
	nova_pessoa.nome = 'Henrique'
	
	puts nova_pessoa
	
	# Caso eu tente passar um valor para um atributo que não pode ser escrito, irá ocasionar erro
	# nova_pessoa.sobrenome = 'João'

Também podemos criar nosso próprios métodos como o **calcula_idade** e **maiusculo**

	class Pessoa
	  attr_reader :nome, :sobrenome, :cor_olhos, :cabelo, :idade
	  attr_writer :nome, :idade
	
	  def initialize(nome, sobrenome, cor_olhos, cabelo, idade)
	    @nome = nome
	    @sobrenome = sobrenome
	    @cor_olhos = cor_olhos
	    @cabelo = cabelo
	    @idade = idade
	  end
	
	  def to_s
	    "Nome:#{@nome}  Sobrenome:#{@sobrenome}  Cor dos olhos:#{@cor_olhos}  Cabelo:#{@cabelo} Idade:#{@idade}"
	  end
	
	  def calcula_idade
	    case @idade
	      when 0..10
	        puts 'criança'
	      when 11..17
	        puts 'adolescente'
	      when 18..60
	        puts 'adulto'
	      when 61..120
	        puts 'idoso'
	      else
	        puts 'xiiii, essa deve ser a pessoa mais velha do mundo.'
	    end 
	  end
	
	end
	
	
	class String
	  def maiusculo
	    upcase
	  end
	end
	
	nova_pessoa = Pessoa.new(:nome, :sobrenome, :cor_olhos, :cabelo, :idade)
	
	# O attr_write me permite como usuário gravar uma info
	nova_pessoa.nome = 'Henrique'
	
	nova_pessoa.idade = 25
	
	puts nova_pessoa
	
	puts nova_pessoa.calcula_idade
	
	# Chama o método maiusculo
	puts nova_pessoa.nome.maiusculo


> Adicionamos o método maiusculo dentro da class string, pois é seu tipo de objeto e nosso outro metodo .upcase recebe somente objetos da classe string.

