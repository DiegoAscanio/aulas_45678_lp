<style>
  section {
    background: #fff url(./img/background.png) no-repeat center center;
    background-size: cover;
  }

  .transparent {
    background-color: transparent!important;
  }

  section.transparent img {
    background-color: transparent!important;
  }

  .transparent-table-tr-td-th {
    background-color: rgba(0, 0, 0, 0.0) !important;
  }

  .cabecalho {
    position: absolute;
    top: 10%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 48px;
    font-weight: bold;
  }

  .conteudo {
    top: 30%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 28px;
    text-align: justify;
  }

  .conteudo-absoluto {
    position: absolute;
    top: 30%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 28px;
    text-align: justify;
  }
  
  .large {
    font-size: 36px;
  }

  .normal {
    font-size: 22px;
  }
  .regular {
    font-size: 18px;
  }
  .small {
    font-size: 16px;
  }
  .footnotesize {
    font-size: 14px;
  }
  .scriptsize {
    font-size: 12px;
  }
  .tiny {
    font-size: 10px;
  }
  .bold {
    font-weight: bold;
  }
  .center {
    text-align: center;
  }
  section.lead p {
    text-align: justify;
  }
  section.lead h1 {
    text-align: center;
  }
  section.lead h2 {
    text-align: center;
  }
  
  .grid-50-50 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    text-align: justify;
  }

  .grid-66-33 {
    display: grid;
    grid-template-columns: 2fr 1fr;
    text-align: justify;
  }

  .grid-33-66 {
    display: grid;
    grid-template-columns: 1fr 2fr;
    text-align: justify;
  }

  .grid-element {
    margin-left: 5%;
    margin-right: 5%;
  }
  img[alt=grid-img] {
    width: 100%;
  }
  img[alt=curta] {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 40%;
  }

</style>

<link href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/themes/prism.min.css" rel="stylesheet" />
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/prism.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/components/prism-c.min.js"></script>



<!-- _class: lead -->
# Linguagens de Programação
## Tipos de Dados, Subprogramas, Paradigma Orientado a Objetos e Tratamento de Exceções

Elaborado pelo prof. M. Sc. Diego Ascânio Santos [ascanio@cefetmg.br](ascanio@cefetmg.br) com base no material do prof. Dr. Andrei Rimsa Álvares [andrei@cefetmg.br](andrei@cefetmg.br)


---

## Roteiro

1. Tipos de Dados
2. Subprogramas
3. Programação Orientada a Objetos
4. Tratamento de Exceções


---

## Tipos de Dados

<div class="normal">

### Introdução

- Valores e tipos de dados são cruciais em linguagens de programação.
    - Definem como os dados são armazenados, processados e manipulados.
- Através da categorização dos dados em tipos, a segurança do código é garantida, pois, operações entre tipos incompatíveis são restritas.
- Melhoram legibilidade e manutenção do código.
- Essenciais para a modelagem de dados complexos:
    - [Pois] Permitem a criação de estruturas de dados complexas, bem como, níveis avançados de abstração em programação.


</div>


---

## Tipos de Dados

### Classificação

Podem ser classificados em dois grupos:

1. Primitivos.
2. Compostos.


---

## Tipos de Dados

<div class="normal">

### Primitivos 

- São básicos e atômicos, não podendo ser divididos em partes menores.
    - Exemplos: `int`, `float`, `bool`, `str`, `NoneType`
- A implementação dos tipos de dados variam de linguagem para linguagem.
    - O tamanho de um `int` em C é definido no tempo de implementação, regido pela arquitetura da máquina.
    - Em java o tamanho de um `int` é de 32 bits (4 bytes) independente da arquitetura.
- Muitas linguagens suportam a definição de tipos ordinais de dados, como `enum` em C e C++, considerados no nosso contexto, como tipos primitivos.
    - Estes tipos de dados são equivalentes às definições matemáticas de conjunto domínio — um conjunto restrito de valores os quais uma variável pode assumir — e quando criamos uma variável de tipo enumerável, seus valores estão restritos ao conjunto domínio (ordinal) definido.
        - Exemplo de enum: `enum DiaDaSemana {SEGUNDA, TERCA, QUARTA, QUINTA, SEXTA, SABADO, DOMINGO};`
        - Exemplo de uso: `DiaDaSemana dia = TERCA;`
    

</div>


---

## Tipos de Dados

<div class="normal">

### Compostos 

- Formados por dois ou mais tipos de dados simples.
    - Exemplos: registros (structs), vetores, matrizes, listas, etc.
- Produzidos a partir de produtos cartesianos, uniões, mapeamentos, dentre outros.
- Possuem cardinalidade: número de elementos distintos que fazem parte do tipo.
- Para o nosso propósito, é suficiente vermos somente os tipos de dados compostos definidos à partir dos produtos cartesianos.

</div>


---

## Tipos de Dados

<div class="normal">

### Compostos - Produto Cartesiano

- Representam a combinação de valores de tipos diferentes em tuplas:

![](https://i.imgur.com/UUU10l2.png)

- Cardinalidade:
    \\( \\# (n_{1} \times n_{2} \times \ldots \times n_{k}) = \\# n_{1} \times \\# n_{2} \times \ldots \times \\# n_{k} \\)

</div>


---

## Tipos de Dados

<div class="normal">

### Compostos - Produto Cartesiano

- Exemplos de produtos cartesianos: registros em Pascal, structs (estruturas) em C, tuplas em Python.

- Exemplos de produtos cartesianos em C:

<div class="grid-50-50">

<div class="grid-element">
<pre>
<code class="language-c">
struct empregado {
    int codigo;
    char nome[50];
    float salario;
};
</code>
</pre>
</div>
<div class="grid-element">
<pre>
<code class="language-c">
struct ponto {
    int x;
    int y;
};
</code>
</pre>
</div>

</div>

- Em Linguagens exclusivamente orientadas a objetos, como Java, os produtos cartesianos são chamados de classes.

</div>



---

<!-- _class: lead -->
## Produto Cartesiano

<div class="regular">

**Exemplo**

```c
struct data {
    int dia, mes, ano;
};
```

**Inicialização**
```c
struct data d = { 7, 9, 1999 };
```

**Acesso**
```c
printf("%d/%d/%d\n", d.dia, d.mes, d.ano);
```

**Cardinalidade**
```
#INTEGER x #INTEGER x #INTEGER
```

</div>



---

## Tipos de Dados

### Síntese

<div class="regular">

- Tipos de dados podem ser primitivos ou compostos.
- Essenciais para determinar como os dados serão operados no contexto de um programa.
- Apesar da totalidade de tipos compostos e primitivos não ter sido abordada, é apresentado o diagrama da hierarquia de tipos, presente na [aula 4](http://rimsa.com.br/documents/lectures/decom009/lessons/Aula04.pdf) do professor Andrei Rimsa Álvares.

![curta](https://i.imgur.com/wdvl7ez.png)

</div>


---

<!-- _class: lead -->
# Verificação de Tipos


---

## Verificação de Tipos

- Existe para garantir a compatibilidade de tipos entre os objetos que estão sendo usados no programa.
    - Ou, em outras palavras, que os operandos de um operador sejam de tipos compatíveis.
- Pode ser realizada em tempo de compilação.
    - Nesse caso é chamada de **verificação estática** — C, C++, Java, Pascal, etc.
- Ou, pode ser realizada em tempo de execução.
    - Nesse caso é chamada de **verificação dinâmica** — Python, Ruby, Javascript, Lua, dentre outras.


---

## Verificação de Tipos
### Linguagens Fortemente (Fracamente) Tipadas

<div class="regular">

- Uma linguagem é fortemente tipada se operações entre tipos incompatíveis são proibidas. Exemplos de linguagens fortemente tipadas: Java, Python, C#.
- Exemplos de linguagens fracamente tipadas: JavaScript, PHP, C, C++.

</div>


---

### Verificação de Tipos — Linguagens Fortemente (Fracamente) Tipadas

<div class="regular">

- Aqui vemos a diferença entre linguagens fortemente e fracamente tipadas:

</div>

<iframe width="100%" height="100%" src="https://diegoascanio.github.io/jupyterlite/lab?path=diferenca_linguagens_fortemente_e_fracamente_tipadas.ipynb"></iframe>


---

## Verificação de Tipos - Equivalência de Tipos

<div class="regular">

Alguns tipos de dados são equivalentes, ou seja, podem ser convertidos de um para o outro sem perda de informação. Por exemplo, um inteiro pode ser convertido para um real sem perda de informação, mas um real não pode ser convertido para um inteiro sem perda de informação. A conversão de um tipo de dado para outro é chamada de coerção.

Isto porquê, apesar de serem tipos de dados distintos (inteiros e reais), ainda assim, faz sentido executar operações entre variáveis inteiras e reais, por exemplo.

Com isso, entendemos que em operações que resultam em um número inteiro, o tipo inteiro é equivalente a um real, mas, não o contrário, pois, para converter um real para um inteiro, seria necessário aplicar coerção ao valor real, o que resultaria em perda de informação.

</div>


---

## Verificação de Tipos - Inferência de Tipos

- Inferência de tipos é a capacidade de deduzir o tipo das variáveis a partir do contexto em que se encontram em linguagens estáticamente (e fortemente) tipadas.
    - Desta forma, não é necessário especificar todos os tipos das variáveis em um programa.
- Java \\(( \geq 10)\\), Julia, Rust, Scala, Kotlin, TypeScript, Go, Haskell, dentre outras, são exemplos de linguagens que possuem inferência de tipos.
- C (até sua revisão 23) não possui inferência de tipos.


---

<!-- _class: lead -->
# Subprogramas


---

## Subprogramas - Abstrações

Abstrações são conceitos essenciais para a programação. Elas permitem que o programador se concentre em um problema de cada vez, sem se preocupar com detalhes irrelevantes, tais quais: como os dados são armazenados na memória, de qual origem são obtidos, como são processados, quais operações em baixo nível são necessárias para que uma instrução seja executada, dentre outros.

Da definição, podemos entender a abstração como um conceito e a implementação como sua concretização. No fim das contas, ninguém quer saber se o pato é macho, todo mundo quer é o ovo. A abstração é o ovo, a implementação é o pato. Subprogramas entregam nossos ovos através de suas implementações, concretizadas por funções e procedimentos.


---

## Subprogramas - Modularização

Por permitirem a abstração — que habilita a modelagem do problema de múltiplas formas — os subprogramas possuem como vantagem possibilitar que o programador possa dividir para conquistar: dividir o problema em partes menores, mais simples, e resolver cada uma delas de forma independente, usando quantos subprogramas forem necessários, para no fim, agregar todos os resultados e resolver o problema como um todo.


---

<div class="normal">

## Subprogramas - Funções e Procedimentos

Os subprogramas podem ser divididos em dois tipos: funções e procedimentos. A principal diferença entre eles é que as funções retornam um valor, enquanto os procedimentos não retornam nada. Além desta, entendemos também que as funções não podem estar submetidas a **efeitos colaterais**, ou seja, que para uma dada entrada de dados em seus parâmetros, seus retornos sejam sempre os mesmos, independente de qualquer outro fator externo à função, entretanto, nem sempre tais efeitos colaterais são evitáveis.

Na perspectiva da modularização entendemos os procedimentos mais como agregadores de comandos e operações (que não retornam valores) para abstrair, encapsular, esconder, modularizar partes não essenciais do problema, ao passo que as funções, são utilizadas quando, além de todos os predicados pertinentes aos procedimentos, é necessário retornar valores de operações ou de estados (verdadeiro, falso, positivo, negativo, etc.) necessários em alguma parte do programa principal, sem a qual o problema não possa ser resolvido.

</div>


---

## Exemplos de Funções e Procedimentos

<div class="grid-50-50 footnotesize">

<div class="grid-element">

Exemplo prático para diferenciarmos funções e procedimentos.

Considere que você é o RH de uma micro empresa com 15 funcionários.

É necessário construir um relatório associando funcionários e os impostos que deverão pagar com base nos salários que recebem.

Para isso:

1. Construa uma função que calcule o imposto a ser pago, com base na seguinte tabela:


| Salário | Alíquota (taxa) |
| ------- | --------------- |
|De 1.903,99 até 2.826,65|7,50%|
|De 2.826,66 até 3.751,05|15%|
|De 3.751,06 até 4.664,68|22,50%|
|Acima de 4.664,68|27,50%|

2. Construe um procedimento que:
2.1 Solicite o nome do funcionário
2.2 Solicite o salário do funcionário
2.3 Imprima o nome e o imposto a ser pago pelo funcionário, separados por uma tabulação

3. Chame este procedimento para cada um dos 15 funcionários da empresa

</div>
<div class="grid-element">

```javascript
function calcularImposto(salario) { // função
    if (salario < 1903.99)
        return 0
    else if (salario >= 1903.99 && salario < 2826.66)
        return salario * 0.075
    else if (salario >= 2826.66 && salario < 3751.06)
        return salario * 0.15
    else if (salario >= 3751.06 && salario < 4664.68)
        return salario * 0.225
    else
        return salario * 0.275
}
function relatorio(){ // procedimento 
    nome = prompt('Insira o nome do funcionario: ');
    salario = prompt('Insira o salario do funcionario: ');
    alert(nome + '\t' + calcularImposto(salario));
}
var i = 0;
while (i < 15) {
    relatorio();
    i ++;
}
```

</div>

</div>
