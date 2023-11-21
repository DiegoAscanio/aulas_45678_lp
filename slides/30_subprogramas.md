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
