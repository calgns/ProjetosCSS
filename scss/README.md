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

## Estilização dos flocos

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
 

```scss

```