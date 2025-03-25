# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove.

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta:
Alternativa a) Se rodarmos o console.log antes da variável, o programa não vai reconhecer o valor dela, mostrando undefined. Com a variável y acontece algo semelhante, mas por ser tipo let, aparece erro.


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```
______
a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

alternativa b) O código foi feito para verificar se os dois valores da função não são 0. Caso não sejam, eles são somados e o resultado é mostrado no console.log, mas no código só é conferido o valor do b, ignorando o a. Ainda por cima caso o número seja zero, como no código original, ele vai se encaixar na função e gerar um erro. Para resolver isso o operador lógico deve ser trocado por && (e), fazendo o erro acontecer somente no caso de 0 nos dois valores.

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

alternativa b) O pensamento mais intuitivo é que o código iria imprimir 1000, mas por conta da falta do break após o case "eletrônico", o valor de 1000 é substituído por 200.
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24

alternativa d) O resultado será 24 já que o método map() percorre cada elemento do array numeros e retorna um novo array onde cada elemento foi multiplicado por 2, depois o método filter() seleciona apenas os números maiores que 5, e o método reduce() soma os valores restantes resultando no número 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

alternativa c) Esse é o conteúdo mostrado por conta do splice que escolhe qual posição do array que será modificada, índice inicial onde a alteração começa, posição inicial 1 que é o segundo elemento maçã, depois são escolhidos os dois elementos que serão removidos. Depois os elementos "abacaxi", "manga" que serão inseridos no lugar dos removidos. Deixando na ordem "banana", "abacaxi", "manga", "laranja".
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

alternativa b) O JavaScript tem essa função e ela funciona como descrito na afirmação 1. Sim, a herança é implementada através da palavra-chave extends, mas ela usa uma sintaxe mais parecida com (POO).
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

alternativa a) A classe funcionario, usa extend e super para acessar as classes nome e idade. A afirmativa 2 também está correta, a função apresentar da classe pessoa é sim sobreescrita pela da classe funcionario, mas por conta de usar o super funciona.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

alternativa a) O polimorfismo permite que diferentes objetos do mesmo tipo respondam de maneiras distintas. A afirmação está correta, pois a sobrecarga de métodos é uma das técnicas utilizadas para implementar esse conceito.
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Código concertado:

```javascript
function somaArray(numeros) {
    let soma = 0; // Inicializando a variável soma corretamente

    for (let i = 0; i < numeros.length; i++) { // Usando .length corretamente
        soma += 2 * numeros[i]; // Acumulando a soma corretamente
    }
    
    return soma;

    console.log(somaArray([1, 2, 3, 4]));
}

```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.90; // Aplica 10% de desconto
    }
}

// Classe derivada (subclasse)
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); // Chama o construtor da superclasse
        this.autor = autor;
    }

    // Sobrescreve o método calcularDesconto para aplicar 20%
    calcularDesconto() {
        return this.preco * 0.80;
    }
}

// Criando instâncias das classes
let produtoGenerico = new Produto("Fone de Ouvido", 100);
let livro1 = new Livro("JavaScript Avançado", 150, "Carlos Silva");

console.log(`${produtoGenerico.nome} com desconto: R$ ${produtoGenerico.calcularDesconto().toFixed(2)}`);
console.log(`${livro1.nome} de ${livro1.autor} com desconto: R$ ${livro1.calcularDesconto().toFixed(2)}`);
```

Deve ser criada uma Superclasse produto que define nome e preço, depois um método que aplica o desconto de 10%. Depois criar uma Subclasse Livro que usa extends Produto para herdar os atributos nome e preco, além de criar um atributo autor e sobrescrever calcularDesconto() para aplicar 20%. No construtor da classe Livro, usamos super(nome, preco) para chamar o construtor da classe pai (Produto), garantindo que nome e preco sejam inicializados corretamente.

O poliformismo se deve ao livro que herda de produto, mas modifica o comportamento do método herdado.