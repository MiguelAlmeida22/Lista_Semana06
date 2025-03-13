# Respostas das Questões da Lista de Exercícios da Semana 06

#### 1.  **_A) A saída será undefined seguido de erro._**

**Justificativa:** O programa tenta realizar um "console.log(x)" sendo que a variável x não tinha sido definida anteriormente, somente depois da linha do "console.log(x), então a variável está indefinida. O mesmo ocorre para "console.log(y), pois a variável não tinha sido declarada anteriormente ao pedido de impressão. Então, a saída seria um undefined seguido de um erro.

#### 2.  **_A) Substituir if (a || b === 0) por if (a === 0 || b === 0)._**

**Justificativa:** No código original, a condição "if (a || b === 0)" verifica apenas se "a" é truthy ou se "b" é igual a 0. Assim, quando chamamos "soma(2, 0)", a condição retorna verdadeira por causa de "a" (2 é truthy) e gera um erro, mesmo que a intenção seja verificar se algum é exatamente 0. Corrigindo para "if (a === 0 || b === 0)", garantimos que cada variável seja comparada explicitamente a 0, fazendo o código funcionar.

#### 3.  **_B) O código imprime 200._**

**Justificativa:** No caso "eletrônico", não há um break após atribuir "preco = 1000". Assim, o código continua para o case seguinte "("vestuário")", atribuindo preco = 200 e então executa o break. Portanto, a função retorna 200 quando chamada com "eletrônico".

#### 4.  **_D) 24._**

**Justificativa:** Primeiro, o método map multiplica cada elemento do array "[1, 2, 3, 4, 5]" por 2, resultando em "[2, 4, 6, 8, 10]". Em seguida, o filter seleciona apenas os números maiores que 5, ou seja, "[6, 8, 10]". Por fim, o reduce soma esses valores, começando com o acumulador "0: 6 + 8 + 10 = 24".

#### 5.  **_C) ["banana", "abacaxi", "manga", "laranja"]_**

**Justificativa:** "Splice" é usado para remover e/ou adicionar elementos de um array. No código, "lista.splice(1, 2, "abacaxi", "manga")" remove 2 elementos a partir do índice 1 (ou seja, "maçã" e "uva") e insere "abacaxi" e "manga" nesse mesmo local. Assim, o array passa de "["banana", "maçã", "uva", "laranja"]" para "["banana", "abacaxi", "manga", "laranja"]".

#### 6.  **_A) As duas afirmações são verdadeiras, e a segunda justifica a primeira._**

**Justificativa:** 

**Afirmação I**: Verdadeira. A herança em JavaScript é usada para compartilhar métodos e propriedades entre classes. Isso permite reutilizar código e criar hierarquias de classes que evitam a repetição desnecessária, promovendo maior organização e eficiência.

**Afirmação II**: Verdadeira. Em JavaScript, a palavra-chave "extends" é usada para implementar a herança. Uma classe pode usar "extends" para herdar os métodos e propriedades de outra classe, tornando esta uma forma prática e direta de implementar herança.

A segunda afirmação justifica a primeira porque explica como a herança é implementada em JavaScript.

#### 7.  **_A) I e II são verdadeiras._**

**Justificativa:** A classe "Funcionario" herda de "Pessoa", permitindo que acesse diretamente os atributos "nome" e "idade" definidos no construtor da classe "pai". Além disso, o método apresentar() na classe "Funcionario" sobrescreve o método de "Pessoa" e, ao usar "super.apresentar()", chama a implementação da classe "pai" antes de executar seu próprio código. Já a afirmação III é falsa, pois o JavaScript suporta herança de classes, permitindo exatamente essa abordagem.

#### 8.  **_B) A asserção é verdadeira e a razão é falsa._**

**Justificativa:** A asserção é verdadeira, pois o polimorfismo permite que métodos com o mesmo nome se comportem de forma diferente dependendo do objeto que os chama, já a razão é falsa, pois JavaScript não permite que se defina vários métodos com o mesmo nome e parâmetros diferentes. Em vez disso, é utilizado a sobrescrita de métodos para alcançar o polimorfismo.

#### 9.  (Utilizei o ChatGPT para me auxiliar nessa questão)

``` javascript
function somaArray(numeros) {
    // Declarei a variável 'soma' para acumular o resultado, iniciando em 0.
    let soma = 0;

    // Para o tamanho do array usei 'numeros.length' em vez de 'numeros.size'.
    // Declarei a variável 'i' com let para evitar problemas de escopo.
    for (let i = 0; i < numeros.length; i++) {
        // Usei '+=' para acumular o dobro de cada número e para somar ao valor anterior de 'soma'.
        soma += 2 * numeros[i];
    }
    // Retorna o valor total acumulado.
    return soma;
}

console.log(somaArray([1, 2, 3, 4])); // Deve imprimir 20
```
**O que foi corrigido:**

1. **Tamanho do array:** O código original usa numeros.size, mas em JavaScript o tamanho de um array é obtido com a propriedade length.

2. **Variável de acumulação:** A variável soma não estava sendo declarada antes de ser usada. Declaramos let soma = 0; para iniciar a soma.

3. **Acumulação incorreta:** No loop, o código sobrescrevia soma com 2 * numeros[i] a cada iteração. Para somar os valores dobrados, usamos soma += 2 * numeros[i];.

4. **Declaração da variável de controle:** Declaramos a variável i com let para evitar a criação de uma variável global.

#### 10.  (Utilizei o ChatGPT para me auxiliar nessa questão)

``` javascript
// Classe Produto: define atributos e um método para calcular desconto de 10%
class Produto {
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }

  // Método que retorna o preço com 10% de desconto
  calcularDesconto() {
    return this.preco * 0.9; // Aplica 10% de desconto
  }
}

// Classe Livro: herda de Produto e sobrescreve o método calcularDesconto()
// Aplica um desconto de 20% aos livros.
class Livro extends Produto {
  constructor(nome, preco, autor) {
    // Chama o construtor da classe Pai (Produto) para inicializar nome e preco
    super(nome, preco);
    this.autor = autor;
  }

  // Método sobrescrito que retorna o preço com 20% de desconto
  calcularDesconto() {
    return this.preco * 0.8; // Aplica 20% de desconto
  }
}

// Exemplo prático de uso:
const produto = new Produto("Cadeira", 100);
console.log(`Preço com desconto (Produto): R$ ${produto.calcularDesconto()}`);

const livro = new Livro("Romance", 100, "Autor");
console.log(`Preço com desconto (Livro): R$ ${livro.calcularDesconto()}`);
```
**Explicação:**
A classe "Produto" define atributos básicos como nome e preco e possui um método "calcularDesconto()" que aplica um desconto fixo de 10% sobre o preço. A classe "Livro" herda de "Produto" utilizando a palavra-chave "extends", o que permite que ela tenha acesso aos atributos e métodos da classe "pai". No construtor de "Livro", usamos "super(nome, preco)" para inicializar os atributos herdados e adicionamos um novo atributo "autor". Além disso, a classe "Livro" sobrescreve o método "calcularDesconto()" para aplicar um desconto de 20% específico para livros. Essa técnica é um exemplo prático de polimorfismo, onde o mesmo método "calcularDesconto()" se comporta de forma diferente dependendo do objeto (Produto ou Livro).














