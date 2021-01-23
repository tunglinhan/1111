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
            p5.stroke(189, 242, 227);
            p5.fill(4, 15, 217);
            p5.beginShape();
            p5.vertex(80,290);
            p5.vertex(360,290);
            p5.vertex(320,310);
            p5.vertex(40,310);
            p5.vertex(80,290);
            p5.endShape();
            p5.line(180,310,180,210);
            p5.line(220,290,220,190);
            p5.line(180,210,220,190);
            p5.line(180,220,220,200);
            p5.line(180,230,220,210);
            p5.line(180,240,220,220);
            p5.line(180,250,220,230);
            p5.line(215,232,215,193);
            p5.line(210,234,210,195);
            p5.line(205,236,205,198);
            p5.line(200,238,200,200);
            p5.line(195,242,195,203);
            p5.line(190,244,190,205);
            p5.line(185,246,185,207);
            p5.line(150,290,110,310);
            p5.line(290,290,250,310);
            p5.line(60,300,130,300);
            p5.line(340,300,270,300);
            p5.pop();
            p5.push();
            let b = p5.map(p5.mouseX, 0, p5.width, 0, 30);
            p5.translate(130,280);
            p5.rotate(p5.radians(-35+b));
            p5.stroke(242, 48, 48);
            p5.fill(2, 30, 115);
            p5.line(0,0,0,-65);
            p5.rect(0,-15,8,30,3);
            p5.ellipse(0,-85,40,50)
            p5.pop();
            p5.push();
            let c = p5.map(p5.mouseX, 0, p5.width, 0, 30);
            p5.translate(270,280);
            p5.rotate(p5.radians(5+c));
            p5.stroke(242, 48, 48);
            p5.fill(2, 30, 115);
            p5.line(0,0,0,-65);
            p5.rect(0,-15,8,30,3);
            p5.ellipse(0,-85,40,50)
            p5.pop();
            p5.push();
            p5.fill(242, 48, 48);
            p5.stroke(242, 48, 48);
            p5.translate(p5.width/2,p5.height);
            let a = p5.map(p5.mouseX, 0, p5.width, 0, 60);
            p5.rotate(p5.radians(-30+a));
            p5.push();
            p5.ellipse(0,-220,10);
            p5.line(0,-220,0,-238);
            p5.line(0,-220,-5,-238);
            p5.line(0,-220,5,-238);
            p5.line(0,-220,-10,-238);
            p5.line(0,-220,10,-238);
            p5.line(0,-220,-15,-238);
            p5.line(0,-220,15,-238);
            p5.line(-8,-230,8,-230);
            p5.line(-12,-234,12,-234);
            p5.line(-15,-238,15,-238);
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