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
