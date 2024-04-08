<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Image Slider</title>
  <style>
    /* Style for the image slider container */
    .slider-container {
      position: relative;
      max-width: 100%;
      margin: auto;
      overflow: hidden;
    }

    /* Style for the images */
    .slide {
      display: none;
      width: 100%;
      height: auto;
      text-align: center;
    }

    .slide img {
      width: 300px; /* Adjust the width as needed */
      height: auto;
      border-radius: 50%; /* Rounded corners to make it look like a face */
    }

    /* Style for the animal name */
    .animal-name {
      position: absolute;
      bottom: 10px;
      left: 0;
      width: 100%;
      text-align: center;
      color: white;
      font-size: 18px;
      background-color: rgba(0, 0, 0, 0.5);
      padding: 5px;
    }

    /* Style for the navigation arrows */
    .prev, .next {
      cursor: pointer;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: auto;
      padding: 16px;
      margin-top: -22px;
      color: white;
      font-weight: bold;
      font-size: 20px;
      background-color: rgba(0, 0, 0, 0.5);
      border-radius: 0 3px 3px 0;
    }

    .prev {
      left: 0;
      border-radius: 3px 0 0 3px;
    }

    .next {
      right: 0;
      border-radius: 0 3px 3px 0;
    }
  </style>
</head>
<body>

<div class="slider-container">
  <!-- Images -->
  <div class="slide">
    <img src="https://via.placeholder.com/300x300?text=Cat" alt="Cat">
    <div class="animal-name">Cat</div>
  </div>
  <div class="slide">
    <img src="https://via.placeholder.com/300x300?text=Rabbit" alt="Rabbit">
    <div class="animal-name">Rabbit</div>
  </div>
  <div class="slide">
    <img src="https://via.placeholder.com/300x300?text=Dog" alt="Dog">
    <div class="animal-name">Dog</div>
  </div>

  <!-- Navigation arrows -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>

<script>
  let slideIndex = 1;
  showSlides(slideIndex);

  function plusSlides(n) {
    showSlides(slideIndex += n);
  }

  function currentSlide(n) {
    showSlides(slideIndex = n);
  }

  function showSlides(n) {
    let i;
    const slides = document.getElementsByClassName("slide");
    if (n > slides.length) {slideIndex = 1}    
    if (n < 1) {slideIndex = slides.length}
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";  
    }
    slides[slideIndex-1].style.display = "block";  
  }
</script>

</body>
</html>
