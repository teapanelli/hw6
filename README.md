# hw6
code etc for the final

//how can i get the bubbles to avoid the mouse?
//how can i get the object in the back to randomize its position?
//what the hell should the object in the background be?
//what sound should i play??
//what colors should i use?????
var bubbles = [];

function setup() {
  createCanvas(600, 600);

  for (var i = 0; i < 1000; i++) {
    var bubble = {
      x: random(width),
      y: random(height),
      radius: 50
    };
    bubbles.push(bubble);
  }
}

function draw() {
  background(255);

  for (var i = 0; i < bubbles.length; i++) {
    var bubble = bubbles[i];

    if (dist(mouseX, mouseY, bubble.x, bubble.y) < bubble.radius) {
      if (mouseIsPressed) {
        bubbles.splice(i, 1); // remove this bubble!
      }
      fill(255, 200, 200, 200);
    } else {
      noStroke();
      fill(220, 220, 255);
    }

    ellipse(bubble.x, bubble.y, bubble.radius * 2);
    bubble.x += random(-1, 1);
    bubble.y += random(-1, 1);
  
  }
}
