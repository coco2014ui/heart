# heart
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { margin: 0; background: black; display: flex; justify-content: center; align-items: center; height: 100vh; }
    canvas { max-width: 100%; max-height: 100%; }
  </style>
</head>
<body>
<canvas id="c" width="800" height="800"></canvas>
<script>
  const ctx = document.getElementById('c').getContext('2d');
  ctx.translate(400, 400);
  ctx.strokeStyle = 'red';
  let i = 0;

  function draw() {
    for (let step = 0; step < 5; step++) {
      if (i >= 1000) return;
      let x = 15 * Math.pow(Math.sin(i), 3) * 18;
      let y = -(12 * Math.cos(i) - 5 * Math.cos(2*i) - 2 * Math.cos(3*i) - Math.cos(4*i)) * 18;
      ctx.beginPath();
      ctx.moveTo(0, 0);
      ctx.lineTo(x, y);
      ctx.stroke();
      i++;
    }
    requestAnimationFrame(draw);
  }
  draw();
</script>
</body>
</html>
