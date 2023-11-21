## Passagem de Parâmetros — Momento da Ocorrência da Passagem de Parâmetros

<div class="regular">

O momento da passagem de parâmetros refere-se a quando e como os valores dos argumentos são transmitidos aos parâmetros formais de um subprograma. Isso inclui:

**1. Avaliação Imediata (ou Eager Evaluation):** Onde os argumentos são avaliados no momento da chamada do subprograma, antes de entrar no subprograma propriamente dito. Este é o comportamento mais comum em linguagens de programação como Python, Java e C.

**2. Avaliação por Nome (ou Lazy Evaluation):** Os argumentos são avaliados apenas quando o parâmetro correspondente é utilizado no corpo do subprograma. Isso significa que a expressão passada como argumento é reavaliada a cada vez que o parâmetro é acessado.

**3. Avaliação Preguiçosa (Lazy Evaluation):** Similar à avaliação por nome, mas a expressão é avaliada apenas na primeira vez que o parâmetro é acessado e, em seguida, o valor é armazenado para usos subsequentes dentro do mesmo subprograma.

Cada um desses métodos tem implicações diferentes para o desempenho, efeitos colaterais e comportamento geral de um subprograma — não abordados neste semestre da nossa disciplina.

</div>
