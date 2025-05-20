# Ex.08 Design of Interactive Image Gallery

## AIM
  To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS

## Step 1:

Clone the github repository and create Django admin interface

## Step 2:

Change settings.py file to allow request from all hosts.

## Step 3:

Use CSS for positioning and styling.

## Step 4:

Write JavaScript program for implementing interactivit

## Step 5:

Validate the HTML and CSS code

## Step 6:

Publish the website in the given URL.

## PROGRAM:
```
index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Interactive Photo Gallery</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>

  <h1>Interactive Photo Gallery</h1>
<h4>Anu Radha N | 212223230018</h4>

  <div class="gallery-container">
    <div class="gallery-item"><img src="./bike.jpg" alt="Image 1"></div>
    <div class="gallery-item"><img src="./Palamathi Hills.png" alt="Image 2"></div>
    <div class="gallery-item"><img src="./Screenshot 2025-01-12 214937.png" alt="Image 3"></div>
    <div class="gallery-item"><img src="./Screenshot 2025-04-25 210732.png" alt="Image 4"></div>
    <div class="gallery-item"><img src="./Screenshot 2025-04-26 102907.png" alt="Image 5"></div>
  </div>

  <div class="modal" id="modal">
    <span class="close" id="close">&times;</span>
    <img class="modal-content" id="modal-img" alt="Expanded view">
  </div>

  <script src="script.js"></script>

</body>
</html>
```
```
styles.css

body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(to right, #586e90, #9dafc2);
  color: #333;
}

h1 {
  text-align: center;
  padding: 40px 10px 20px;
  font-size: 2.5rem;
  background: linear-gradient(90deg, #9feeea, #d2fe24);
  font-weight: bold;
}

h4 {
    text-align: center;
    font-size: larger;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
    color:#f3ebec;
}
.gallery-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 20px;
  padding: 20px;
  max-width: 1200px;
  margin: auto;
}

.gallery-item img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  border-radius: 14px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
  transition: transform 0.35s, box-shadow 0.35s;
  cursor: pointer;
}

.gallery-item img:hover {
  transform: scale(1.05);
  box-shadow: 0 16px 32px rgba(144, 49, 49, 0.18);
}

.modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.85);
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  max-width: 90%;
  max-height: 80%;
  border-radius: 12px;
  box-shadow: 0 0 30px rgba(255,255,255,0.2);
  animation: zoomIn 0.3s ease;
}

.close {
  position: absolute;
  top: 20px;
  right: 30px;
  font-size: 36px;
  color: #fff;
  font-weight: bold;
  cursor: pointer;
  transition: color 0.3s;
}

.close:hover {
  color: #ffbbbb;
}

@keyframes zoomIn {
  from { transform: scale(0.95); opacity: 0.8; }
  to { transform: scale(1); opacity: 1; }
}

@media (max-width: 600px) {
  .gallery-item img { height: 180px; }
  .close { font-size: 30px; right: 20px; }
}
```
```
document.addEventListener('DOMContentLoaded', () => {
  const modal = document.getElementById('modal');
  const modalImg = document.getElementById('modal-img');
  const closeBtn = document.getElementById('close');

  document.querySelectorAll('.gallery-item img').forEach(img => {
    img.addEventListener('click', () => {
      modal.style.display = 'flex';
      modalImg.src = img.src;
      modalImg.alt = img.alt || 'Expanded Image';
    });
  });

  const closeModal = () => {
    modal.style.display = 'none';
    modalImg.src = '';
  };

  closeBtn.addEventListener('click', closeModal);
  modal.addEventListener('click', e => {
    if (e.target === modal) closeModal();
  });
});
```
## OUTPUT:
![alt text](<Screenshot 2025-05-20 215912.png>)

![alt text](<Screenshot 2025-05-20 215924.png>)
## RESULT
  The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
