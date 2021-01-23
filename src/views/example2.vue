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
        
        p5.setup = () => {
            p5.createCanvas(400, 400);
            p5.rectMode(p5.CENTER);
        };

        p5.draw = () => {
            p5.background(4, 57, 217);
            p5.translate(p5.width/2, p5.height/3);
            p5.push();
            p5.stroke(189, 242, 227);
            let c = p5.map(p5.mouseX, 0, p5.width, 0, 150);
            let d = p5.map(p5.mouseX, 0, p5.width, 90, 0);
            p5.rotate(p5.radians(d));
            p5.line(0,0,0,0+c);
            p5.pop();
            p5.push();
            p5.stroke(189, 242, 227);
            p5.strokeWeight(2);
            p5.fill(2, 30, 115);
            let e = p5.map(p5.mouseX, 0, p5.width, 0, 150);
            let f = p5.map(p5.mouseX, 0, p5.width, 90, 0);
            let g = p5.map(p5.mouseX, 0, p5.width, 0, 10);
            p5.rotate(p5.radians(f));
            p5.ellipse(0,0+e,20);
            p5.push();
            p5.line(0+g,10+e-g,0-g,-10+e+g);
            p5.line(10-g,0+g+e,-10+g,0-g+e);
            p5.pop();
            p5.pop();
            p5.push();
            p5.noStroke();
            p5.fill(242, 48, 48);
            let a = p5.map(p5.mouseX, 0, p5.width, 0, 30);
            p5.rotate(p5.radians(30-a));
            p5.rect(8,0,40,25,10);
            p5.push();
            let b = p5.map(p5.mouseX, 0, p5.width, 0, 90);
            p5.rotate(p5.radians(110-b));
            p5.rect(-3,15,8,35,10);
            p5.rect(-7,10,8,35,10);
            p5.pop();
            p5.push();
            p5.fill(189, 242, 227);
            let x = p5.map(p5.mouseX, 0, p5.width, 10, 0);
            let y = p5.map(p5.mouseX, 0, p5.width, 10, 5);
            p5.rotate(p5.radians(30+y));
            p5.rect(20,-65+x,25,100,8);
            p5.pop();
            p5.push();
            let z = p5.map(p5.mouseX, 0, p5.width, 10, 5);
            p5.rotate(p5.radians(90+z));
            p5.rect(-8,10,8,20,10);
            p5.pop();
            p5.pop();
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