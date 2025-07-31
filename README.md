<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Envelope in the Middle</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      height: 100vh;
      background: #f2f2f2;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
    }

    .envelope-wrapper {
      position: relative;
      width: 200px;
      height: 120px;
      perspective: 1000px;
    }

    .envelope {
      width: 100%;
      height: 100%;
      position: relative;
      background: #fff;
      border: 2px solid #555;
      border-radius: 6px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.6s ease;
    }

    .envelope.open .flap {
      transform: rotateX(-150deg);
    }

    .flap {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 60%;
      background: #ccc;
      transform-origin: top;
      transform: rotateX(0deg);
      transition: transform 0.6s ease;
      z-index: 2;
    }

    .letter {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      padding: 10px;
      text-align: center;
      background: white;
      color: #333;
      z-index: 1;
      opacity: 0;
      transition: opacity 0.6s ease;
    }

    .envelope.open .letter {
      opacity: 1;
    }
  </style>
</head>
<body>

<div class="envelope-wrapper">
  <div class="envelope" onclick="toggleEnvelope(this)">
    <div class="flap"></div>
    <div class="letter">
      <h3>You Got a Letter!</h3>
      <p>This is a message inside the envelope. 📝</p>
    </div>
  </div>
</div>

<script>
  function toggleEnvelope(el) {
    el.classList.toggle('open');
  }
</script>

</body>
</html>
