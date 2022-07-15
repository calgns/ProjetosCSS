# CSS Loaders
### OBS: aqui terá apenas 3 exemplos de loaders, mas existem milhares aprecie-os com moderação.

<br/>
<h2>Gradient/Rainbow</h2>

<div style="width:400px; height:400px;">
  <img src="../../imgs/css/loaders/rainbow.gif" alt="Rainbow Loader">
  
</div>

## receita do Rainbow 

### rainbow
estrutura do codigo
```css
  .Rainbow {
      top: 10vh;
      width: 200px;
      height: 200px;
      margin: 0 auto;
      overflow: hidden;
      position: relative;
      border-radius: 50%;
      box-shadow: 0px 20px 35px rgba(0, 0, 0, 0.5);
    }
  
```
efeito especial depois de colocar essa parte você decide quais cores e velocidade de giro

OBS: geralmente tamanho tem que ser 250px a mais que o da estrutura
```css
  .Rainbow::before {
    content: "";
    height: 450px;
    width: 450px;
    top: -125px;
    left: -125px;
    border-radius: 12px;
    position: absolute;
    background: conic-gradient(
      hsl(342, 100%, 50%),
      hsl(34, 100%, 50%),
      hsl(56, 100%, 56%),
      hsl(125, 82%, 56%),
      hsl(246, 80%, 60%),
      hsl(298, 98%, 56%),
      hsl(360, 100%, 45%)
    );
    animation: spin 1s infinite linear;
  }

  @keyframes spin {
    100% {
      transform: rotate(-360deg);
    }
  }
```

aqui você coloca o texto, 95% de tamanho para aparecer a borda carregando e display grid pra centralizar
```css
  .Rainbow::after {
    content: "TOO RASH";
    position: absolute;
    background-color: #1c1b29;
    border-radius: 50%;
    font-size: 1.3rem;
    height: 95%;
    width: 95%;
    top: 3%;
    left: 2.5%;
    color: aliceblue;
    font-family: century, helvetica, arial, sans-serif;
    letter-spacing: 6px;
    place-items: center;
    display: grid;
  }
```


