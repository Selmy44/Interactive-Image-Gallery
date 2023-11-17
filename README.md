# Interactive-Image-Gallery
This is a Interactive Image Gallery website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Interactive Image Gallery</title>
  <style>
    .gallery {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }
    .gallery img {
      width: 100%;
      height: auto;
      transition: transform 0.3s ease-in-out;
      cursor: pointer;
    }
    .gallery img:hover {
      transform: scale(1.1);
    }
  </style>
</head>
<body>

<div class="gallery">
  <img src="image1.jpg" alt="Image 1" onclick="openModal('image1.jpg', 'Image 1 Description')">
  <img src="image2.jpg" alt="Image 2" onclick="openModal('image2.jpg', 'Image 2 Description')">
  <img src="image3.jpg" alt="Image 3" onclick="openModal('image3.jpg', 'Image 3 Description')">
  <!-- Add more images with appropriate filenames and descriptions -->
</div>

<!-- Modal for displaying the enlarged image and description -->
<div id="modal" style="display: none;">
  <span onclick="closeModal()" style="position: absolute; top: 15px; right: 15px; cursor: pointer;">&times;</span>
  <img id="modalImg" style="width: 100%; height: auto;">
  <p id="caption" style="text-align: center; margin-top: 10px;"></p>
</div>

<script>
  function openModal(imageSrc, description) {
    const modal = document.getElementById('modal');
    const modalImg = document.getElementById('modalImg');
    const captionText = document.getElementById('caption');
    
    modal.style.display = 'block';
    modalImg.src = imageSrc;
    captionText.textContent = description;
  }

  function closeModal() {
    const modal = document.getElementById('modal');
    modal.style.display = 'none';
  }
</script>

</body>
</html>
