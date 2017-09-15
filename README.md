# LP-Scripts
Scripts feitos em LP 1003

## Conceitos Bacanas

### html
Conteúdo do site. Desde textos e imagens até códigos

### javascript
Linguagem de programação que a gente usa.

Com ela é possível executar códigos pelo navegador.

### canvas
Onde a gente desenha. A tela do pintor.

Exemplo:
```html
<canvas id="meuCanvas" width="800" height="600"></canvas>
<script>
var canvas = document.getElementById("meuCanvas");
// outros códigos vão aqui
</script>
```

### context
O carinha que desenha!

Exemplo:
```javascript
var context = canvas.getContext("2d");
```

### fillRect
O DESENHO!

Exemplo:
```javascript
context.fillRect(posicaoX, posicaoY, largura, altura);
// Lembrando que a posição (0,0) começa no canto *superior esquerdo* da tela.
```
Exemplo completo com outras formas básicas [aqui](https://github.com/matheuslessarodrigues/LP-Codes/blob/master/desenhos-base.html)

### fillStyle
A cor do desenho

Exemplo:
```javascript
context.fillStyle = "red"; // a partir dessa linha, todos os desenhos são vermelhos
// Lembrando que o fillStyle apenas surte efeitos nos comandos de desenho que vêm *depois* dele.
```

### variável
Uma _caixa_ onde você pode guardar _valores_

Exemplo:
```javascript
var nomeDaVariavel = "texto"; // o "var" indica que estamos criando a variável
var outraVariavel = 42;
context.fillRect( outraVariavel, 0, 50, 50 ); // apenas escrever o nome da variável faz a gente usar seu valor
```

### prompt
Pegar valores do usuário

Exemplo:
```javascript
var minhaVariavel = parseInt( prompt( "texto que mostra pro usuario" ) ); // aparecerá uma caixa pro usuário escrever um valor
// minhaVariavel agora tem o valor que o usuário escreveu
```

### animação
Estrutura base para fazer desenhos animados com javascript
```javascript
var canvas = document.getElementById("meuCanvas");
var context = canvas.getContext("2d");

// declaração de variáveis ficam aqui
var x = 0;

function draw() {
  // limpa o canvas  
  context.clearRect(0,0,800,600);

  // desenha um quadrado na posição determinada pela variável x
  context.fillRect(x, 50, 100,100);
  
  // "move o quadrado para a direita"
  x = x + 1;

  // prepara pra desenhar novamente
  requestAnimationFrame(draw);
}
draw();
```
Exemplo completo [aqui](https://github.com/matheuslessarodrigues/LP-Codes/blob/master/animation.html).

### condições (_if_)
Controla o fluxo do programa. O código dentro das chaves (_{}_) apenas é executado caso a condição dentro do _if_ ser verdadeira.

Exemplo:
```javascript
var num = parseInt(prompt("Escreve um número aí")); // pega um número do usuário
if( num < 100 )
{
  // apenas desenha o retângulo se o número
  // que o usuário escrever for menor que 100
  context.fillRect(50, 50, 100,100);
}
else
{
  // esse trecho de código executa apenas
  // quando a condição for falsa
}
```
