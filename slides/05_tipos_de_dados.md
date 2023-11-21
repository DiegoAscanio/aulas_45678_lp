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
