function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
let cor;

let posicaoHorizontal;

let posicaoVertical;

let rastros = []; // Array para armazenar os rastros

let maxRastros = 50; // Número máximo de segmentos do rastro

function setup() {

    createCanvas(400, 400);

    background(100, 0, 0);

    cor = color(random(0, 255), random(0, 255), random(0, 255));

    posicaoHorizontal = 200;

    posicaoVertical = 200;

}

function draw() {

    // Não limpamos a tela aqui para manter os rastros

    fill(cor);

    circle(posicaoHorizontal, posicaoVertical, 50);

    // Adiciona a posição atual ao array de rastros

    rastros.push({ x: posicaoHorizontal, y: posicaoVertical, c: cor });

    // Remove o rastro mais antigo se exceder o tamanho máximo

    if (rastros.length > maxRastros) {

        rastros.shift();

    }

    // Desenha todos os rastros armazenados

    for (let i = 0; i < rastros.length; i++) {

        fill(rastros[i].c);

        circle(rastros[i].x, rastros[i].y, 50);

    }

    // Atualiza a posição do círculo

    if (mouseX < posicaoHorizontal) {

        posicaoHorizontal -= 1;

    } else if (mouseX > posicaoHorizontal) {

        posicaoHorizontal += 1;

    }

    if (mouseY < posicaoVertical) {

        posicaoVertical -= 1;

    } else if (mouseY > posicaoVertical) {

        posicaoVertical += 1;

    }

    // Muda a cor do círculo ao clicar

    if (mouseIsPressed) {

        cor = color(random(0, 255), random(0, 255), random(0, 255));

    }

}
