<template>
  <div class="slider-container">
  <div class="slider-inner">
    <img src="https://cress.gigsalad.com/images/performer-scroll-profiles.png" alt="Image 1">
    <!-- Add more image elements as needed -->
  </div>
</div>
</template>

<style>
.slider-container {
  width: 100%;
  height: 100%; /* Adjust height as needed */
  overflow: hidden;
}

.slider-inner {
  width: 100%; /* Adjust width based on the number of images or desired sliding distance */
  animation: slide 60s linear infinite; /* Adjust animation duration as needed */
}

@keyframes slide {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-60%); /* Adjust sliding distance based on the width of the inner div */
  }
}

</style>