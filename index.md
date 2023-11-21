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
## Tipos de Dados, Verificação de Tipos e Subprogramas

Elaborado pelo prof. M. Sc. Diego Ascânio Santos [ascanio@cefetmg.br](ascanio@cefetmg.br) com base no material do prof. Dr. Andrei Rimsa Álvares [andrei@cefetmg.br](andrei@cefetmg.br)


---

## Roteiro

1. Tipos de Dados
2. Verificação de Tipos
3. Subprogramas


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

2. Construa um procedimento que:
2.1 Solicite o nome do funcionário
2.2 Solicite o salário do funcionário
2.3 Imprima o nome e o imposto a ser pago pelo funcionário, separados por uma tabulação

3. Chame este procedimento para cada um dos 15 funcionários da empresa

</div>
<div class="grid-element">

<!-- _class: lead -->
## Solução

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

É claramente observável a diferença entre funções e procedimentos a partir do exemplo acima, pois, o procedimento relatório funcionou como um agregador (abstrator) de instruções sem retornar valores, ao passo que a função calcularImposto retorna valores sem apresentar — no caso ideal — efeitos colaterais.

</div>

</div>


---

## Subprogramas - Parâmetros

<div class="regular">

Apesar de ainda não termos mencionado parâmetros, no exemplo anterior vimos uma função que recebia um parâmetro — calcularImposto — e um procedimento que não recebia nenhum parâmetro — relatorio.

Antes de entrarmos em detalhes, é importante ressaltar que parâmetros de forma algum distinguem funções de procedimentos, pois, existem funções que não recebem parâmetros, como a função `toString` em javascript, e procedimentos que recebem parâmetros, como o procedimento `alert` também em javascript.

Avançando na discussão, **parâmetros são valores que podem ser passados para funções e procedimentos, sendo que esses valores podem ser utilizados dentro da função ou procedimento, como se fossem variáveis locais**. Quando uma função ou procedimento é chamado, os valores passados para os parâmetros são chamados de argumentos.

Existem duas maneiras de enxergar os parâmetros:
    - Como expressões que produzem o(s) argumento(s) — **denominados parâmetros de chamada ou parâmetros reais**;
    - Como variáveis locais que denotam o(s) argumento(s) no interior da subrotina — **denominados parâmetros formais**.

</div>


---

## Parâmetros reais x Parâmetros formais

- Parâmetros reais: expressões que produzem os argumentos;
- Parâmetros formais: identificadores que denotam os argumentos no interior da subrotina;

<div class="grid-50-50 regular">

<div class="grid-element">

```javascript
//funcao
function area(raio) {
    return Math.PI * raio * raio;
}

//chamadas
area(5);
area(a + b);
```

</div>

<div class="grid-element">

| Tipo | Exemplo |
|------|---------|
| Argumento | 5 e o resultado de a + b |
| Parâmetro real | 5 e a expressão a + b |
| Parâmetro formal | raio |

</div>

</div>


---

<div class="regular">

## Correspondência entre parâmetros formais e parâmetros reais

A correspondência geralmente é posicional, ou seja, o primeiro parâmetro formal corresponde ao primeiro parâmetro real, o segundo parâmetro formal corresponde ao segundo parâmetro real, e assim por diante.

Mas pode ser realizada por palavras chaves, especificando-se o nome do parâmetro formal correspondente ao parâmetro real para cada argumento, como também, pode admitir valores padrões.

Em python a correspondência é posicional, mas pode ser realizada por palavras chaves, admite-se valores padrões e pode ser mista, como veremos a seguir:

```python
def soma(a, b, c = 0):
    return a + b + c

# correspondencia posicional
# 3 corresponde ao parâmetro a e 4 corresponde ao parâmetro b
soma(3, 4) # 7

# correspondencia por palavras chaves
soma(b = 5, a = 9) # 14

# correspondencia posicional e por palavras chaves
soma(3, b = 4) # 7

# em todos os casos acima c assumiu um valor padrão, agora vamos explicitar o valor de c em correspondencia posicional
soma(3, 4, 5) # 12

# e agora em correspondencia por palavras chaves
soma(c = 5, a = 9, b = 11) # 25
```

</div>


---

## Parâmetros - Impactos da Ausência de Parâmetros

<div class="regular">

A ausência de parâmetros causam impactos negativos nos seguintes aspectos do código:

- **Legibilidade**: a ausência de parâmetros torna o código mais difícil de ser lido, pois, o leitor precisa entender o código para saber quais são os valores que estão sendo utilizados, já que não existem menções aos identificadores usados na função.

- **Manutenibilidade**: a ausência de parâmetros torna o código mais difícil de ser mantido, pois, o desenvolvedor precisa entender o código para saber quais são os valores que estão sendo utilizados.

- **Reusabilidade e Confiabilidade**: a ausência de parâmetros torna o código menos reutilizável e confiável, pois, os parâmetros auxiliam a deduzir a natureza dos valores que estão sendo utilizados e por consequência, a deduzir o comportamento da subrotina que está sendo chamada.

</div>


---

## Passagem de parâmetros 

- Compreendem as maneiras de transmitir informações (parâmetros) para os subprogramas chamados.

- Três aspectos importantes governam a passagem de parâmetros:
    - **Direção da passagem**
    - **Mecanismo de implementação**
    - **Momento de Ocorrência**.


---

## Direção da passagem de parâmetros

<div class="regular">

1. Entrada (input): Parâmetros de entrada são aqueles fornecidos ao subprograma pelo chamador. Eles são usados pelo subprograma em suas operações internas, mas não são modificados para reflexo no chamador.

2. Saída (output): Parâmetros de saída são aqueles que o subprograma utiliza para retornar dados para o chamador. Eles podem ser modificados dentro do subprograma e essas modificações são refletidas no chamador.

3. Bidirecional: Parâmetros bidirecionais podem ser utilizados tanto para receber dados de entrada quanto para enviar dados de saída. Eles permitem que o subprograma receba dados, os modifique e então devolva os dados modificados ao chamador.

</div>


---

## Passagem de Parâmetros - Direção da Passagem

<div class="regular">

1. Parâmetros de entrada

Exemplo em javascript:

```javascript
alert("Olá Mundo!");
```

2. Parâmetros de saída

Exemplo em matlab:
```matlab
function [x,y] = pol2cart(theta,rho)
```

3. Parâmetros de entrada e saída 
Exemplo em python:
```python
def inserir_valor_no_meio_do_vetor(vetor, valor):
    meio = len(vetor) // 2
    vetor.insert(meio, valor)
```

</div>


---

## Passagem de Parâmetros - Mecanismos de Passagem

<div class="grid-50-50 small">

<div class="grid-element">

1. Passagem por cópia (valor)

O valor do argumento é copiado para o parâmetro formal do subprograma. Qualquer modificação feita ao parâmetro dentro do subprograma não afeta o argumento original no chamador.

Exemplo em javascript:
```javascript
function incrementa(x) {
    x = x + 1;
    return x;
}
var b = 5;
alert(incrementa(b)); // 6
alert(b); // 5
```

</div>

<div class="grid-element">

2. Passagem por referência

Ao invés de passar uma cópia do valor, a passagem por referência envia um endereço de memória do argumento. Isso significa que o subprograma opera diretamente no dado original. As alterações feitas no parâmetro afetam diretamente o argumento no chamador. Este método é eficiente em termos de memória para grandes estruturas de dados, mas pode levar a efeitos colaterais indesejados se não for usado com cuidado.

Exemplo em C:
```c
void incrementa(int *x) {
    *x = *x + 1;
}
int main() {
    int b = 5;
    incrementa(&b);
    printf("%d\n", b); // 6
    return 0;
}
```

</div>

</div>


---

## Passagem de Parâmetros - Mecanismos de Passagem

<div class="small grid-50-50">

<div class="grid-element">

3. Passagem por nome

Este método envolve a substituição do parâmetro formal pelo argumento real cada vez que o parâmetro é usado no subprograma. Não é uma cópia do valor nem um endereço de memória que é passado, mas a expressão do argumento em si. Isso significa que a expressão é avaliada cada vez que o parâmetro é acessado, o que pode levar a resultados diferentes se o estado do argumento mudar entre essas avaliações.

Exemplo em PseudoCódigo:
```
procedure increment(x)
    x = x + 1
end procedure

procedure printTwice(int n) 
    print n
    print n
end procedure
```

</div>
<div class="grid-element">

Se chamarmos printTwice com um parâmetro por nome, como printTwice(increment(y)), aqui está o que aconteceria:

1. Suponha que y seja inicialmente 5.
2. Na primeira chamada de print dentro de printTwice, increment(y) é avaliado, incrementando y para 6 e retornando esse valor. Portanto, 6 é impresso.
3. Na segunda chamada de print, increment(y) é avaliado novamente, incrementando y para 7 e retornando esse valor. Então, 7 é impresso.

Portanto, a saída seria "6 7", mesmo que intuitivamente possamos esperar "6 6". Isso ocorre porque, na passagem por nome, a expressão é reavaliada cada vez que o parâmetro é acessado, ao contrário da passagem por valor, onde o valor inicial seria usado em todas as chamadas. Isso demonstra como a passagem por nome pode levar a resultados diferentes e possivelmente inesperados dependendo do estado do argumento entre avaliações.

Atualmente este modelo de passagem de parâmetros não é usado nas linguagens modernas, como Java, C# e Python. Podemos encontrar este modelo em ALGOL.

</div>

</div>


---

## Passagem de Parâmetros — Momento da Ocorrência da Passagem de Parâmetros

<div class="regular">

O momento da passagem de parâmetros refere-se a quando e como os valores dos argumentos são transmitidos aos parâmetros formais de um subprograma. Isso inclui:

**1. Avaliação Imediata (ou Eager Evaluation):** Onde os argumentos são avaliados no momento da chamada do subprograma, antes de entrar no subprograma propriamente dito. Este é o comportamento mais comum em linguagens de programação como Python, Java e C.

**2. Avaliação por Nome (ou Lazy Evaluation):** Os argumentos são avaliados apenas quando o parâmetro correspondente é utilizado no corpo do subprograma. Isso significa que a expressão passada como argumento é reavaliada a cada vez que o parâmetro é acessado.

**3. Avaliação Preguiçosa (Lazy Evaluation):** Similar à avaliação por nome, mas a expressão é avaliada apenas na primeira vez que o parâmetro é acessado e, em seguida, o valor é armazenado para usos subsequentes dentro do mesmo subprograma.

Cada um desses métodos tem implicações diferentes para o desempenho, efeitos colaterais e comportamento geral de um subprograma — não abordados neste semestre da nossa disciplina.

</div>


---

<!-- _class: lead -->
# Planejamento para o restante do semestre


---

## Planejamento para o restante do semestre

<div class="regular">

1. Paradigma Funcional (28/11)
2. Seminários sobre orientação a objetos e tratamento de exceções (05/12 - valor: 25 pontos no laboratório, 20 pontos na teórica)
    1. Classes e Objetos
    2. Herança e Polimorfismo
    3. Diferenças entre encapsulamento e modificadores de acesso (public, private, protected).
    4. Tratamento de exceções.
3. Prova II (12/12 - valor: 30 pontos)
4. Listas de exercícios (valor: 20 pontos)
5. Trabalho 3 Laboratório (Até 14/12 - valor: 25 pontos)

</div>
