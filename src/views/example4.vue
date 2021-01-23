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
            p5.push();
            p5.translate(150,100);
            let b = p5.map(p5.mouseX, 0, p5.width, 0, 30);
            p5.rotate(p5.radians(30-b));
            p5.fill(242, 48, 48);
            p5.stroke(242, 48, 48);
            p5.strokeWeight(5);
            p5.line(0,0,0,135);
            p5.rect(0,85,40,100,10);
            p5.push();
            p5.fill(255);
            p5.rect(0,85,40,25,5);
            p5.pop();
            p5.pop();
            p5.push();
            let e = p5.map(p5.mouseX, 0, p5.width, 0, 20);
            let f = p5.map(p5.mouseX, 0, p5.width, 0, 25);
            p5.translate(230+e,210);
            p5.rotate(p5.radians(-10+f));
            p5.fill(255);
            p5.stroke(255);
            p5.rect(0,0,25,10,2);
            p5.rect(0,-22,30,40,10);
            p5.rect(-15,-20,10,25,5);
            p5.pop();
            p5.push();
            let c = p5.map(p5.mouseX, 0, p5.width, 0, 50);
            let d = p5.map(p5.mouseX, 0, p5.width, 0, 25);
            p5.translate(250-c,210);
            p5.rotate(p5.radians(10-d));
            p5.fill(242, 48, 48);
            p5.stroke(242, 48, 48);
            p5.rect(0,0,25,10,2);
            p5.rect(0,-22,30,40,10);
            p5.rect(-15,-20,10,25,5);
            p5.pop();
            p5.push();
            p5.noStroke();
            p5.fill(189, 242, 227);
            p5.rect(200,280,240,50,5);
            p5.push();
            p5.fill(255);
            p5.rect(200,280,240,25);
            p5.rect(150,100,60,10,2);
            p5.pop();
            p5.push();
            p5.fill(2, 30, 115);
            p5.stroke(189, 242, 227);
            p5.rect(90,240,10,80,5);
            p5.rect(310,240,10,80,5);
            p5.line(100,210,300,210);
            p5.line(100,220,300,220);
            p5.line(100,230,300,230);
            p5.line(100,240,300,240);
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