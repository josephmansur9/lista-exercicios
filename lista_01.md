# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
**a) A saída será undefined seguido de erro**

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

**A saida sera undefined seguido por erro, porque a variavel x é criada com var é atribuida um valor somente depois de ser chamada pela primeira vez, resultando em undefined. O let por outro lado criou uma variavel y, mas ela não pode ser acessada antes de ser decladrada, resultando em um erro.**


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

**a) Substituir if (a || b === 0) por if (a === 0 || b === 0)**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**A funcao || verifica somente se a variavel A é true ou diferente de 0 ou se B é estritamente igual a 0, a gente precisa de um operador que compara cada variavel indivudualmente**


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

**b) O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

**Ele imprime 200 porque ele vai entrar no primeiro case, que é eletronico attribuindo 1000 pro preco, depois ele vai pro outro case, vestuário e substitui pelo valor dele, que é 200. E só depois ele para porque tem um break em baixo, se nao tivesse ele continuaria a mudar o preco.**


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

**d) 24**

**Alternativa d, a funcao map vai executar a multiplicacao para todas variaveis no Array, ou seja 1 * 2, 2 * 2, 3 * 2 etc... 2, 4, 6, 8, 10 respectivamente. o filter filtra as variaveis diferentes da condicao, ou seja x precisa ser maior que 5 entao 6, 8 e 10. O reduce vai fazer a somatoria das variaveis do array dando só um valor, sendo 0 o inicio da conta ela fica 6+8+10.**

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

**c) ["banana", "abacaxi", "manga", "laranja"]**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**o splice vai substituir as variaveis, como o codigo ta chamando as variaveis 1,2 maca e uva respectivamente os dois sao substituidos por abacaxi e manga**

______

**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


**a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

**a palavra-chave extends cria uma relacao de heranca entre classes, onde a classe mãe passa código para as subclasses, isso é o que esta escrito na primeira afirmacao por isso alternativa A**
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

**a) I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**a classe funcionario extends a classe pessoa, por isso ela pode acessar os atributos nome e idade. Por que o método apresentar da classe funcionario foi chamada depois, ela sobre-escreve o apresentar da classe pessoa. O super entretanto consegue chamar o "apresentar" da classe mãe, a classe pessoa.**

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**a assercao é verdadeira, por exemplo voce tem uma classe chamada frutas com subclasses maca, banana e pera; cada subclasse tem um valor diferente atribuido para ele, se voce criar uma funcao pedindo o valor cada subclasse iria interagir diferentemente. A razao é falsa pois o método de sobrecarga não funciona no JavaScript.**

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

function somaArray(numeros) {

    //precisa definir a soma primeiro, e ela vai comecao em 0
    let soma=0
    //defini a variavel i que vai ser um contador. Ele comeco em 0 e enquanto o i for menor que o tamanho da lista de numeros que agora é 5, ele vai atribuir na soma o valor do numero de indice [i] multiplicado por 2
    for (let i = 0; i < numeros.length; i++) {
        soma += 2*numeros[i];
    }
    //aqui ele "devolve" a soma
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));

**Eu primeiro tive que criar uma variavel soma, que iniciasse com 0 antes de poder usar ela. Também adicionei o let na variavel "i" para que ela fosse criada. Por fim mudei o numeros.size para numeros.length**
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.


class Product {
    constructor(nome, preco) {
        this.nome = nome; 
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.9
    }
}

class Livro extends Product {
    constructor(nome, preco) {
      super(nome, preco);
    }
  
    calcularDesconto() {
      return this.preco * 0.8;
    }
}

**eu criei uma classe produto com os atributos nome e peco, o método vai aplicar um desconto de 10%, multiplicando o preco do produto por 0.9. A classe livro herda a classe produto alterando o método do desconto, aplicando agora um desconto de 20%.**