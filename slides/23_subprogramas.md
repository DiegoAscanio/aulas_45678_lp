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
