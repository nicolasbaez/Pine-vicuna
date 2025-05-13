# Pine-vicuna
Why don't you like dancing

![buh](https://github.com/nicolasbaez/Pine-vicuna/blob/main/xp049.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
a = 0;
k = 0;
draw = (_) => {
  clear();
  rotateX(k);
  rotateY(k / 2);
  noFill();
  stroke(255, 0, noise(k) * 255);
  beginShape();
  for (z = w; z > -w; z -= 2) {
    r = noise(z * 0.01) * w * 0.5;
    push();
    vertex(r * cos(a), r * sin(a), z);
    pop();
    a += 0.1;
  }
  endShape();
  if (k == 0) saveGif("xp049.gif", 1256, { delay: 0, units: "frames" });
  k += 0.01;
};
