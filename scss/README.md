# Flocos de Neve
### OBS: nesse codigo estou usando scss para facilitar a escrita do codigo.
### OBS2: meu pc é fraco pra gravar, os flocos não pesam o site é apenas o meu pc que é fraco na hora de gravar.


<br/>
<h2>Efeito Nevando</h2>

<div style="width:600px; height:600px;">
  <img src="../imgs/scss/snowing.gif" alt="Rainbow Loader">
</div>

# receita de Flocos De Neve

## Criando fundo Chamativo

```scss
@charset "utf-8";

body{
  overflow: hidden;
  min-width: 100vw;
  min-height: 100vh;
  position: relative;
  background-color: #4158D0;
  background: linear-gradient(-5deg, #00DBDE 0%, #FC00FF 95%) no-repeat;
}

```

## Estilizar os flocos

```scss
.flake {
  --size: 2vw;
  width: var(--size);
  height: var(--size);
  background: blanchedalmond;
  border-radius: 50%;
  position: absolute;
  top: -5vh;


  $odds: (1,3,5,7);
  @each $u in $odds {
    &:nth-child(#{$u}n) {
      filter: blur(#{$u + 1}px);
    }
  }

  @for $i from 1 through 50 {
    &:nth-child(#{$i}){
      --size: #{random(4) * 0.3}vw;
      --left-in: #{random(20)-10}vw;
      --left-out: #{random(20)-10}vw;
      left: #{random(100)}vw;
      animation: cair #{5 + random(20)}s linear infinite;
      animation-delay: -#{random(20)}s;
    }
  }
}
```
#### o --size está vinculado a width e height o que significa que se você o altera em qulquer parte do codigo a width e height daquela parte especifica vai ser alterada.

#### o $odds está adicionando o efeito de desfoque, embaçar a cada 1 floco dando o valor 2px, a cada 3 com valor de 4px e por ai vai até de 7 em sete.

#### o @for está add uma posição aleatoria para cada um deles alem de estar chamando a animation.

```scss

```