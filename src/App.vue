<template class="w-[100vw] overflow-hidden">
  <header class="w-[100vw] overflow-clip fixed top-0" style="z-index: 150;">

    <div class="px-5 md:px-10 w-full h-[80px] bg-[#002d18] flex gap-5 items-center">
      <a href="#top"><img class="mx-5 cursor-pointer" src="./assets/lacoste-logo.png" width="48" height="22" alt="Logo lacoste"></a>
      <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block ml-2 mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">MEN</a>
      <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">WOMEN</a>
      <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">KIDS</a>
      <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-lime-700 hover:text-lime-500 font-sans link" href="">SALE</a>
      <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">DISCOVER</a>
      
      <div :class="{ 'w-full': isFocused, 'w-2/3 lg:w-1/2': !isFocused }" 
        class="transition-all duration-300 ml-2 h-[60%] 
        bg-white items-center overflow-hidden px-2 relative
        hidden md:flex">
        <img src="./assets/lupa.png" width="22" height="auto" alt="">
        <input 
          :value="searchBar"
          @input="$emit('update:searchBar', $event.target.value)" 
          @focus="isFocused = true" @blur="isFocused = false" 
          type="text" class="border-none outline-none bg-transparent p-2 w-full" 
          placeholder="Find a product">
        <span v-if="isFocused" @click="clearInput" id="delete" class="absolute right-2 flex items-center justify-center text-white cursor-pointer">X</span>
      </div>
      
      <div class="w-40 ml-auto md:w-80 h-full flex justify-around items-center">
        <img class="h-5 filter invert cursor-pointer" src="./assets/facebook.png" alt="">
        <img class="h-5 filter invert cursor-pointer" src="./assets/instagram.png" alt="">
        <img class="h-5 filter invert cursor-pointer" src="./assets/social.png" alt="">
        <img class="h-5 filter invert cursor-pointer" src="./assets/telegram.png" alt="">
      </div>
    </div>

    <div v-if="!isFocused" id="secondNav" style="z-index: -10; transition: top 0.7s;" class="w-full bg-[#002d18] items-center justify-center hidden md:flex flex-wrap relative py-2" >
      <div class="flex justify-around w-3/4 min-[1416px]:w-1/2">
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">NEW IN</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">CLOTHING</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">SHOES</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">BAGS & LEATHER GOODS</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">ACCESORIES</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">SPORT</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">UNDERWEAR</a>
        <a  :class="{ 'link': true, 'fade-out': isFocused }" class="hidden md:block mr-2 transition ease-in-out delay-50 duration-300 font-medium text-gray-400 hover:text-white font-sans link" href="">SALE</a>
      </div>
    </div>
    <div v-else id="secondNav"></div>

    <div id="searchBarMobile" style="z-index: -10; transition: top 0.7s;" class="w-full border h-[48px] bg-white items-center flex md:hidden relative px-10">
      <img src="./assets/lupa.png" width="22" height="auto" alt="">
      <input 
        :value="searchBar"
        @input="$emit('update:searchBar', $event.target.value)" 
        @focus="isFocused = true" @blur="isFocused = false" 
        type="text" class="border-none outline-none bg-transparent p-2 w-full" 
        placeholder="Find a product">
      <span v-if="isFocused" @click="clearInput" id="delete" class="flex items-center justify-center text-white cursor-pointer">X</span>
    </div>

  </header>
  <body id="top" class="w-[100vw] overflow-clip">
    
    
    <!-- 3d LOGO -->
    <div class="spin-container">
      <div class="spinning-object">
        <!-- Front Image -->
        <img src="https://i.pinimg.com/originals/3e/61/85/3e618566c193683b5db603932abae87f.png" alt="Front Image" class="front-image">

        <!-- Curved images for 3D effect -->
        <img src="https://i.pinimg.com/originals/3e/61/85/3e618566c193683b5db603932abae87f.png" alt="Middle Layer" class="middle-image">
        <img src="https://i.pinimg.com/originals/3e/61/85/3e618566c193683b5db603932abae87f.png" alt="Back Layer" class="back-image">
      </div>
    </div>
    <!-- end 3d LOGO -->
     
    <div class="w-full h-[128px] bg-[#002d18] block md:hidden"></div>

    <video style="z-index: 100;" id="myVideo" class="border-none border-transparent border-0 relative" autoplay muted playsinline>
      <source src="./assets/lacoste-landing-heritage-home-video.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div class="w-full h-[205px] py-10 relative z-10 bg-white overflow-hidden" style="z-index: 50;">
      <p class="text-center font-sans font-extrabold text-xs scale-y-90 m-5">LACOSTE STORY</p>
      <p class="text-center font-serif font-medium text-xl md:text-6xl scale-150">90 YEARS OF STYLE</p>
    </div>


    <div class="scroll-container w-[100vw] overflow-clip">
      <div class="text-container w-[100vw]">
        <p class="scrolling-text font-serif font-light scale-x-125 text-[#002d18]">RENÉ LACOSTE</p>
      </div>
    </div>
    
    <div class="w-full absolute top-[200vh] md:top-[200vh] overflow-clip">
      
      <div class="h-[878px] w-full bg-[#0e210b] overflow-hidden flex items-center justify-center" style="z-index: -5;">
        <div>
          <p class="text-white text-center font-sans font-extrabold text-sm scale-x-125">The champion turned inventor</p>
          <p class="text-white text-center font-serif font-medium text-xl md:text-7xl scale-150 m-16">RENÉ LACOSTE,<br> THE ORIGINAL <br> CROCODILE</p>
          <p style="text-wrap: balance;" class="px-2 md:px-44 text-white text-center font-sans font-extrabold text-sm scale-y-90">Once upon a time, there was an extraordinary man who revolutionised his era. A tennis legend and genius inventor, René Lacoste is a myth. This is the story of the man who turned his nickname into one of the most popular brands in the world...</p>
        </div>
      </div>


      <video style="z-index: 50;" id="myVideo" class="w-full border-none border-transparent border-0 relative" autoplay muted playsinline loop>
        <source src="./assets/lacoste-landing-heritage-chapter1-zoom1-1.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>


      <div class="w-full md:w-[420px] py-10 p-2 md:p-none mx-none mt-24 md:mx-24 md:mt-4">
        <p class="font-sans text-2xl">
          <b>A story about a suitcase</b><br>
        </p>
        <p class="font-sans text-sm leading-loose">
          1923. "If I win, you give me that suitcase", says tennis champion René Lacoste to his team captain as he sets his sights on a crocodile skin suitcase. The bet was lost but the adventure was started. The American press, fascinated by the young man's tenacity, published the anecdote. René was now known as "the crocodile"... and became a legend in the making.
        </p>
        <button class="coolButton my-5">The man of many talents →</button>
      </div>


      <div class="w-full flex flex-wrap gap-5 justify-around fotoContainer">
        
        <div class="w-full md:w-1/3 block md:sticky top-0 fotoItem">
          <img src="./assets/lacoste-croc.png" class="w-full md:w-[488]"  alt="">
          <div class="w-full p-2 md:p-none">
            <p class="font-sans text-2xl">
              <b>A crocodile signed Robert George</b><br>
            </p>
            <p class="font-sans text-sm leading-loose">
              1927. The stylist Robert George has fun drawing a crocodile and shows his sketches to his friend, René Lacoste. The tennis champion cannot resist the opportunity to wear the animal, the symbol of his international recognition, and has it embroidered on his white blazer. He wears it before each match. And it doesn't go unnoticed.
            </p>
          </div>
        </div>

        <div class="w-full md:w-7/12 justify-center">
          <img src="./assets/lacoste-polo.jpg" class="w-full justify-center" alt="">
          <div class="w-full md:w-[420px] p-2 md:p-none">
            <p class="font-sans text-2xl">
              <b>Putting a logo on a garment. A Lacoste invention.</b><br>
            </p>
            <p class="font-sans text-sm leading-loose">
              1933. The industrialist André Gillier helps René Lacoste develop the knit of the special tennis shirt he has designed. It is white and bears his emblem embroidered on the chest. No one has ever dared and his friends try to dissuade him, but René Lacoste perseveres... Instantly recognisable, welcome to the first ever logo on a garment. The crocodile.
            </p>
          </div>
        </div>

      </div>

      <video id="myVideo" class="border-none border-transparent border-0 relative z-20" autoplay muted playsinline loop>
        <source src="./assets/lacoste-landing-heritage-chapter1.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
    </div> <!--absolute div -->


  </body>
</template>

<script>

export default {
  data() {
    return {
      searchBar: '',
      isFocused: false
    }
  },
  mounted() {
    const video = document.getElementById('myVideo');
    video.addEventListener('ended', function() {
      video.currentTime = video.duration; // stop on last frame
      video.controls = false; // hide controls
    });
  },
  methods: {
    clearInput() {
      console.log(this.searchBar)
      this.searchBar = ''
    }
  }
}

var prevScrollpos = window.pageYOffset;
window.onscroll = function() {
  var currentScrollPos = window.pageYOffset;
  var secondNav = document.getElementById("secondNav");
  if (prevScrollpos > currentScrollPos) {
    document.getElementById("searchBarMobile").style.top = "0";
    secondNav.style.top = "0";
  } else {
    document.getElementById("searchBarMobile").style.top = "-50px";
    secondNav.style.top = ((secondNav.offsetHeight * -1)+'px');
  }
  prevScrollpos = currentScrollPos;
}
</script>

<style>
  html { scroll-behavior: smooth; }
  body{
    /*overflow-x: hidden;*/
    width: 100vw !important;
    overflow-x: hidden;
  }
  .link {
    transition: opacity 1s ease-in-out; /* add transition to opacity */
  }

  .link.fade-out {
    opacity: 0; /* set opacity to 0 when input is focused */
    display: none;
  }

  #delete {
    justify-content: center;
    width: 20px; /* add this */
    height: 20px;
    background-color: #000; /* add this */
    border-radius: 50%; /* add this */
    padding: 0.1em; /* add this */
    color: #fff; /* add this */
  }

  .coolButton {
    background-color: #fff;
    border: 1px solid #002d18;
    border-radius: 50px;
    padding: 10px 20px;
    font-size: 16px;
    font-weight: bold;
    color: #0a2516;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
    position: relative;
    overflow: hidden;
  }

  .coolButton::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    background-color: #002d18;
    border-radius: 50px;
    transition: width 0.15s ease-in-out;
    z-index: -1;
  }

  .coolButton:hover {
    background-color: transparent;
    color: #fff;
  }

  .coolButton:hover::before {
    width: 100%;
  }
  .scroll-container {
    position: relative;
    margin-top: -40vh;
    height: 200vh;
  }
  .text-container {
    z-index: -10;
    position: sticky;
    top: 0;
    animation: scroll-reveal linear forwards;
    animation-timeline: view(80% 0%);
  }
  .scrolling-text {
    text-wrap: nowrap;
    top: 0%; /* Center vertically */
    left: 50%;
    font-size: 600px;
    font-weight: bold;
    animation-range: contain
  }



  @keyframes scroll-reveal {
    from {
      translate: 500vw;
    }
    to {
      translate: -520vw;
    }
  }
  @keyframes scroll-reveal2 {
    from {
      transform: translateX(1500%);
    }
    to {
      transform: translateX(-1500%);
    }
  }

  .fotoContainer .fotoItem {
    animation: fotoScroll linear forwards;
    animation-timeline: view(0% 70%);
  }
  .fotoItem {
    animation-range: contain
  }

  @keyframes fotoScroll {
    from {
      transform: translateY(0);
    }
    to {
      transform: translateY(50%);
    }
  }


  @media only screen and (max-width: 768px) {
    /* styles here will only be applied on small devices */
    .text-container {
      animation: scroll-reveal2 linear forwards;
      animation-timeline: view(70% 0%);
    }

    .fotoContainer .fotoItem {
      animation: none;
      animation-timeline: none;
    }
    .fotoItem {
      animation-range: none
    }
  }

  /* 3d logo animation */
    .spin-container {
      position: fixed; /* Fix the container in the middle of the screen */
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%); /* Center the container */
      width: 200px;
      height: 200px;
      perspective: 1000px; /* For 3D perspective */
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: visible;
      z-index: 20;
  }

  .spinning-object {
      position: relative;
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      /* Scroll-based animation using animation-timeline */
      animation: spin linear forwards;
      animation-timeline: scroll();
  }

  .front-image, .middle-image, .back-image {
      width: 100%;
      height: 100%;
      object-fit: contain;
      position: absolute;
      animation-range: contain;
      top: 0;
      left: 0;

  }

  .middle-image {
      transform: rotateX(5deg) translateZ(4px); /* Middle layer slightly rotated */
  }

  .back-image {
      transform: rotateX(10deg) translateZ(7px); /* Back layer further rotated */
  }

  .scroll-content {
      padding: 20px;
      color: #333;
      text-align: center;
      margin-top: 100vh; /* Push content down to simulate scrolling */
  }

  p {
      font-size: 1.5rem;
  }

  @keyframes spin {
      0% {
          transform: rotateX(0deg);
      }
      100% {
          transform: rotateX(calc(-4 * 360deg));
      }
  }

  


</style>

<head>
  <link rel="icon" type="image/jpg" href="./assets/favicon.jpg">
</head>
