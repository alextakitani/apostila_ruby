


# Apostila: Aprendendo Programar com Ruby

## Instalar

<a name="variavel">**Variáveis**</a>


Podemos pensar nas variáveis como um local onde guardamos coisas pra usar depois. Pense em uma gaveta, podemos imaginar as variáveis como gavetas onde guardamos valores.

No Ruby, para usar uma váriavel, devemos simplesmente atribuir um valor a um nome, ex:

    idade = 1

    fruta = "Maçã"

	soma = 1 + 1


## Primeiros comandos:

**puts** - Exibe texto na tela:

    puts "Olá"



Existem alguns caracteres que são interpretados de forma diferente pelo puts.

Teste os seguintes exemplos:

#{ } - interpolação, interpreta o valor dentro das chaves e converte para texto:

    puts "#{1+1}"

\n - quebra de linha

    puts "Oi.\nTudo bem?"

\t - tabulação

    puts "---\t---\t---"

O puts imprime texto na tela, mas o ruby facilita sua vida convertendo alguns tipos diretamente para texto, teste:

    puts 1

    puts 10+10

    puts Time.now

**gets** - captura o texto digitado.

gets, diferente de puts, é um método que devolve valor. Puts é como se vc estivesse falando, a voz sai de vc. Gets funciona como seus ouvidos, é um comando que recebe dados digitados. Por isso, costumeiramente guardamos este valor digitao em uma [variável](#variaveis).

O código a seguir, quando interpretado, esperará que você digite alguma coisa. E armazenará o valor dentro da variável nome.

    nome = gets
Vamos ao primeiro programa.

Crie um arquivo chamado primeiro.rb com o seguinte conteúdo:

    nome = gets
    puts "Olá, #{nome}"

Salve e rode com:

    ruby primeiro.rb


**Exercícios:**

1) Faça um programa que pergunte o nome e a idade, e mostre a saída:

"Olá, #nome digitado#, você tem #idade digitada# anos".

2 ) Faça um programa que receba o ano de nascimento e mostre a seguinte saída:

"Você tem #idade calculada# anos."

3 ) Faça um programa que receba 2 números e mostre sua soma.

## Operadores

**Aritiméticos**

Supondo que as variáveis a == 10 e b == 20

|Operador|	Descrição| Exemplo|
|--|--|--|
|+|	Adição |	a+b => 30 |
|−|	Subtração|	a - b => -10|
|*|	Multiplicação|	a * b => 200|
|/|	Divisão	| b / a => 2|
|%|	Modulo − Divide a por b e devolve o resto|	b % a => 0
|**	|Potência |	a**b => 100000000000000000000

**Comparação**

|Operador|	Descrição| Exemplo|
|--|--|--|
|==|	Equalidade, retorna true ou false |	1==1 => true |
|.eql?|	Equalidade, retorna true ou false |	1.eql? 4 => false |
|!=|	Diferença retorna true ou false |	5 != 5 => false |
|<|	Menor que |	5 < 10 => true |
|>|	Maior que |	5 > 10 => false |
|<=|Menor ou igual a |	5 <= 5 => true |
|>=|	Maior ou igual a |	10 >= 1 => true |
|<=>|Comparação combinada. |	5 <=> 10 => -1 |

Cabe explicar melhor o operador de Comparação combinada.

Ele compara 2 valores e: retorna 0 se forem iguais.

1 se o primeiro for maior que o segundo e -1 se o segundo for maior que o primeiro.



## Estruturas de Controle
**Condicionais**

**if**  ( se ) - Verifica se uma condição é verdadeira e executa o bloco:

    if 1==1
       puts "1 é igual a 1"
    end

**else** ( senão ) - Usado junto ao if, executado se a condição do if não for verdadeira:

    if 1 > 2
	    puts "1 é maior do que 2"
	else
		puts "2 é maior do que 1"
	end

**elsif** ( senão, se ) - Também usado junto ao if, permite fazer mais uma verificação:

    if 1 == 2
	    puts "1 é igual a 2"
	elsif 1 == 1
		puts "1 é igual a 1"
	else
		puts "não sei de mais nada."
	end

Você pode usar somente um if e um else, mas pode usar quantos elsif quiser.

**unless** - ( a não ser que ) - Testa se a condição é falsa se sim, executa o bloco.

    unless 1 == 0
	    puts "É, parece que 1 não é igual a 0..."
    end

Muitas pessoas questionam a existência do unless, já que o mesmo pode ser alcançado utilizando-se um if, porém em alguns casos ajuda a aumentar a legibilidade do código. O tempo vai te ajudar a decidir quando usar um ou o outro.

**Exercícios:**

1) Faça um programa que pergunte a idade e, dependendo exiba:
"Você é um bebê", "Você é uma criança", "Você é um adulto" ou "Você é um idoso".

2) Faça um programa que peça 2 números e mostre qual o maior.


## Loops

Loops são instruções que dizem ao computador para repetir código até que uma condição seja atendida.

No Ruby temos várias formas de fazer loops.

**while** - ( enquanto) Executa a instrução até que a condição seja false.

```
num = 0
while num < 3 do
   puts num
   num += 1
end
```
O trecho de código acima vai resultar na seguinte saída:

```
0
1
2
```
Vamos acompanhar passo a passo?
Primeiro a variável num é inicializada com o valor 0, então o programa entra no loop.


A condição é verificada, ( **num** < 3 ) traduzindo: o valor de **num** é menor do que 3? Como **num** é zero, a condição é verdadeira, então o programa executa o trecho de código entre o while e end.

puts **num** vai imprimir zero
e **num** += 1, é um atalho.

Tem o mesmo resultado de escrever **num** = **num** + 1. Logo, **num** que era zero passa a ser 1.

O programa volta e testa a condição novamente ( lembra? ele só vai parar a repetição quando a
condição for falsa).

Dessa vez, ( **num** < 3 ) ainda é verdadeiro por que 1 < 3.

E o programa vai continuar repetindo até que **num** seja 3. Como 3 não é maior do que 3, a condição será falsa e o loop terminará.

**Exercício:**

1) Modifique o exemplo acima para que o programa tenha a seguinte saída:

```
0
1
2
3
```

Existem 2 modificações que darão o mesmo resultado, você consegue descobrir quais?

**until** - ( até que ) Executa a instrução até que a condição seja verdadeira.

O until se comporta como o while, com a diferença que a condição deve ser verdadeira.

Enquanto pensamos no while como "repita isso até que a condição x não seja mais verdade", no until pensamos "faça isso até que a condição seja alcançada".

```
num = 0
until num == 3 do
   puts num
   num += 1
end
```
O trecho de código acima vai resultar na seguinte saída:

```
0
1
2
```

Reparou como é a mesma coisa porém escrita de forma diferente? O Ruby tem vários conceitos repetidos, porém com escrita diferente.

Algumas pessoas questionam a existência dessas coisas, dizendo que ter mais de uma forma de representar a mesma coisa gera confusão.

Eu discordo. Assim como os idiomas, as linguagens de programação são feitas para transmitir idéias.

E existem muitas maneiras de dizer as coisas, quando e como dizer fica a critério de as trasmite.
