
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
      width: 100%;
      height: auto;
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
    <img src="https://via.placeholder.com/800x400?text=Dog" alt="Dog">
  </div>
  <div class="slide">
    <img src="https://via.placeholder.com/800x400?text=Cat" alt="Cat">
  </div>
  <div class="slide">
    <img src="https://via.placeholder.com/800x400?text=Rabbit" alt="Rabbit">
  </div>
  <div class="slide">
    <img src="https://via.placeholder.com/800x400?text=Tiger" alt="Tiger">
  </div>

  <!-- Navigation arrows -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>

<script>
  let slideIndex = 0;
  showSlides();

  function plusSlides(n) {
    showSlides(slideIndex += n);
  }

  function currentSlide(n) {
    showSlides(slideIndex = n);
  }

  function showSlides() {
    let i;
    const slides = document.getElementsByClassName("slide");
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";  
    }
    slideIndex++;
    if (slideIndex > slides.length) {slideIndex = 1}    
    slides[slideIndex-1].style.display = "block";  
    setTimeout(showSlides, 2000); // Change image every 2 seconds
  }
</script>

</body>
</html>
  
