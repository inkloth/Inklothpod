<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Inkloth Custom Orders</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      margin: 0;
      padding: 0;
    }
    header {
      background: #111;
      color: white;
      padding: 20px;
      text-align: center;
    }
    .container {
      max-width: 900px;
      margin: 30px auto;
      padding: 20px;
      background: white;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    .preview-box {
      position: relative;
      width: 300px;
      margin: 20px auto;
    }
    #mockup {
      width: 100%;
    }
    #userImage {
      position: absolute;
      top: 90px;
      left: 70px;
      width: 160px;
      display: none;
    }
    input, select, button {
      padding: 10px;
      margin: 10px 0;
      width: 100%;
      max-width: 400px;
      display: block;
    }
    button {
      background: #111;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background: #333;
    }
    footer {
      text-align: center;
      padding: 20px;
      color: #888;
    }
  </style>
</head>
<body>

<header>
  <h1>Inkloth - Custom T-Shirt Orders</h1>
</header>

<div class="container">
  <form action="https://formsubmit.co/your@email.com" method="POST" enctype="multipart/form-data">
    
    <label>Upload Your Design:</label>
    <input type="file" accept="image/*" name="Design Image" onchange="previewImage(event)" required>

    <div class="preview-box">
      <img id="mockup" src="https://i.imgur.com/gckYbsV.png" alt="T-shirt mockup" />
      <img id="userImage" src="" alt="User design preview" />
    </div>

    <label>Your Name:</label>
    <input type="text" name="Name" required>

    <label>Email:</label>
    <input type="email" name="Email" required>

    <label>Phone Number:</label>
    <input type="text" name="Phone" required>

    <label>Size:</label>
    <select name="Size" required>
      <option value="">Select</option>
      <option value="S">Small</option>
      <option value="M">Medium</option>
      <option value="L">Large</option>
      <option value="XL">X-Large</option>
    </select>

    <label>Quantity:</label>
    <input type="number" name="Quantity" min="1" required>

    <label>Additional Notes:</label>
    <input type="text" name="Notes" placeholder="e.g. Color, placement etc.">

    <button type="submit">Place Order</button>
  </form>
</div>

<footer>
  &copy; 2025 Inkloth. All rights reserved.
</footer>

<script>
  function previewImage(event) {
    const userImage = document.getElementById('userImage');
    const file = event.target.files[0];

    if (file) {
      const reader = new FileReader();
      reader.onload = function(e) {
        userImage.src = e.target.result;
        userImage.style.display = 'block';
      };
      reader.readAsDataURL(file);
    }
  }
</script>

</body>
</html>
