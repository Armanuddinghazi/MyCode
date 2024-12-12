<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Phone Motion Counter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 20px;
    }
    #counter {
      font-size: 50px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Phone Motion Counter</h1>
  <p>Move your phone and watch the count increase!</p>
  <div id="counter">0</div>

  <script>
    // Initialize counter
    let counter = 0;

    // Function to update the counter based on phone movement
    function handleMotion(event) {
      // Get acceleration values (X, Y, Z axes)
      const acceleration = event.acceleration;

      // Check if there is any significant movement
      if (acceleration.x > 2 || acceleration.y > 2 || acceleration.z > 2) {
        counter++; // Increase counter on movement
        document.getElementById('counter').textContent = counter;
      }
    }

    // Listen to DeviceMotion event
    window.addEventListener('devicemotion', handleMotion, false);
  </script>
</body>
</html>
