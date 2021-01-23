<template>
  <div class="container">
    <div id="p5Canvas"></div>
  </div>
</template>

<script>
import P5 from 'p5';

export default {
  data() {
    return {
      p5Canvas: null,
    }
  },
  created() {
    const sketch = p5 => {
        let colors = [
	'#0439D9', //amarelo
	'#021E73', //verde
	'#BDF2E3', // azul
	'#F23030', // laranja
  ];
  let brushWeight = 100;
  let angle1 = 0;

  let scalar = 10;
        p5.setup = () => {
            p5.createCanvas(400, 400);
            p5.background(255);
        };

        p5.draw = () => {
            let ang1 = p5.radians(angle1);
	
    let x1 = scalar * p5.cos(ang1);
    let y1 = scalar * p5.sin(ang1);
	// let noiseVal = noise(t);
	
	p5.noStroke();
	p5.push();
	// translate( mouseX, mouseY);
	p5.translate(p5.width / 2, p5.height / 2);
	p5.fill(colors[0]);
	p5.ellipse(x1 - 50, y1 + 50, brushWeight);

	p5.fill(colors[1]);
	p5.ellipse(x1 + 50, y1 +50, brushWeight);

	p5.fill(colors[2]);
	p5.ellipse(x1 +50, y1-50, brushWeight);

	p5.fill(colors[3]);
	p5.ellipse(x1- 50, y1 - 50, brushWeight);
	p5.pop();
	
	angle1 += 2;

	scalar++;
        };
    }

    this.p5Canvas = new P5(sketch, 'p5Canvas');
  },
  unmounted () {
    this.p5Canvas = null;
  },
}
</script>

<style>
#p5Canvas {
  width: 100vw;
  position: relative;
}

main {
  margin: 0 auto;
  width: 90vw;
}
</style>