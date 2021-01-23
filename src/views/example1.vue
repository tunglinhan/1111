<template>
  <div class="container">
    <div class="p5Canvas"></div>
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
            p5.translate(p5.width/2, p5.height/2);
            p5.push();
            p5.stroke(189, 242, 227);
            p5.line(-100,20,100,20);
            let a = p5.map(p5.mouseX, 0, p5.width, 0, 30);
            p5.line(-80, 30, -70+a, 30);
            let b = p5.map(p5.mouseX, 0, p5.width, 0, 20);
            p5.line(0, 30, 10+b, 30);
            let c = p5.map(p5.mouseX, 0, p5.width, 0, 25);
            p5.line(-30, 40, -25+c, 40);
            let d = p5.map(p5.mouseX, 0, p5.width, 0, 15);
            p5.line(50, 40, 60+d, 40);
            p5.pop();
            p5.push();
            p5.noStroke();
            let e = p5.map(p5.mouseX, 0, p5.width, 0, -25);
            p5.fill(242, 48, 48);
            p5.ellipse(-20+e,12,8);
            p5.ellipse(60+e,12,8);
            p5.pop();
            p5.push();
            let f = p5.map(p5.mouseX, 0, p5.width, 0, -25);
            p5.stroke(242, 48, 48);
            p5.fill(2, 30, 115);
            p5.rect(20+f,5, 100,10,5);
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