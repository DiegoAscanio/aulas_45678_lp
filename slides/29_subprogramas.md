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
