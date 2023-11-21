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
