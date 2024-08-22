

<!DOCTYPE html>

<html lang="en">
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.10.0/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.10.0/addons/p5.sound.min.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
    <meta charset="utf-8" />

  </head>
  <body>
    <main>
    </main>
    <script src="sketch.js"></script>
  </body>
</html>





// fantasia, aventura, drama

// a viagem de chihiro, LIVRE, fantasia, aventura
// O feitiço do tempo, Livre, fantasia, comédia
// as aventuras de pi, 10, drama, fantasia, aventura
// depois da chuva, 10, drama
// Homem aranha: no aranhaverso, 10, infantil, ação
// ladrões de bicicleta, 12, drama
// o menino que descobriu o vento, 14, drama


let campoOrcamento;
let campoPraia;
let campoCidadeGrande;

function setup() {
    createCanvas(800, 400);
    createSpan("Sua idade:");
    campoIdade = createInput("5");
    campoFantasia = createCheckbox(" Gosta de fantasia?");
}

function draw() {
    background("white");
    let idade = campoIdade.value();
    let gostaDeFantasia = campoFantasia.checked();
    let recomendacao = geraRecomendacao(idade, gostaDeFantasia);

    fill(color(76, 0, 115));
    textAlign(CENTER, CENTER);
    textSize(38);
    text(recomendacao, width / 2, height / 2);
}

function geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura) {
  if (idade >= 10) {
    if (idade >= 14) {
      return "O menino que descobriu o vento";
    } else {
      if (idade >= 12) {
        if(gostaDeFantasia || gostaDeAventura) {
          return "Homem aranha: no aranhaverso";          
        } else{
         return "Ladrões de bicicleta";
        }
      } else {
        if (gostaDeFantasia) {
          return "As aventuras de pi";
        } else {
          return "Depois da chuva";
        }
      }
    }
  } else {
    if (gostaDeFantasia) {
      return "A viagem de chihiro";
    } else {
      return "O feitiço do tempo";
    }
  }
}




html, body {


  margin: 0;
  padding: 0;
}
canvas {
  display: block;
}
