<template>
  <div class="gallery">
    <div class="gallery__prev"></div>
    <div class="gallery__next"></div>
    <div class="gallery__stream">
      <div class="gallery__item" v-for="flav in seasonalFlavors" :key="flav.monthKey">
        <h2>{{ flav.month }}</h2>
        <div class="d-flex">
          <div class="seasonalSlide round-start col-md-4 align-items-end d-flex ps-3 pb-3" :class="'bg-' + flav.month + 'Bowl'" :id="flav.month + 'Bowl'"><h4 class="blur"><i>{{ flav.flavor }}</i> Bowl</h4></div>
          <div class="seasonalSlide round-end col-md-4 align-items-end d-flex ps-3 pb-3 " :class="'bg-' + flav.month + 'Smoothie'" :id="flav.month + 'Smoothie'"><h4 class="blur"><i>{{ flav.flavor }}</i> Smoothie</h4></div>
        </div>
      </div>

    </div>
    <button class="btn btn-slide prevSlide" @click="movePrev"><i class="mdi mdi-chevron-left text-black fs-1"></i></button>
    <button class="btn btn-slide nextSlide" @click="moveNext"><i class="mdi mdi-chevron-right text-black fs-1"></i></button>

  </div>
</template>

<script>
import { logger } from '../utils/Logger';

export default {
  setup() {
    let seasonalFlavors = [
      {monthKey: 0, month: 'January', flavor: 'TBD', bowlImgSrc: '../assets/img/MarryOnBowl.jpg'},
      {monthKey: 1, month: 'February', flavor: 'Marry On/Wanna Date', bowlImgSrc: 'backgroundImage: url(/assets/img/MarryOnBowl.jpg)', smoothieImgSrc: '../assets/img/MarryOnSmoothie.jpg' },
      {monthKey: 2, month: 'March', flavor: 'Lucky Lagoon', bowlImgSrc: '../assets/img/LuckyLagoonBowl.jpg', smoothieImgSrc: '../assets/img/LuckyLSmoothie.jpg' },
      {monthKey: 3, month: 'April', flavor: 'Bronco Bowl (Carrot Bowl)', bowlImgSrc: '../assets/img/' },
      {monthKey: 4, month: 'May', flavor: 'Lime-O-Licious', bowlImgSrc: '../assets/img/', smoothieImgSrc: '../assets/img/LimeSmoothie' },
      {monthKey: 5, month: 'June', flavor: 'Sunshine', bowlImgSrc: '../assets/img/SunshineBowl.jpg', smoothieImgSrc: '../assets/img/SunshineSmoothie.jpg' },
      {monthKey: 6, month: 'July', flavor: '4th of July', bowlImgSrc: '../assets/img/4thJulyBowl.jpg', smoothieImgSrc: '../assets/img/4thofJulySmoothie.jpg' },
      {monthKey: 7, month: 'August', flavor: 'Dragon', bowlImgSrc: '../assets/img/DragonBowl.jpg',  smoothieImgSrc: '../assets/img/DragonSmoothie.jpg' },
      {monthKey: 8, month: 'September', flavor: 'Customer Pick', bowlImgSrc: '../assets/img/MarryOnBowl', smoothieImgSrc: '../assets/img/MarryOnBowl' },
      {monthKey: 9, month: 'October', flavor: 'AppleFest', bowlImgSrc: '../assets/img/AppleFestBowl.jpg', smoothieImgSrc: '../assets/img/AppleSmoothie.jpg' },
      {monthKey: 10, month: 'November', flavor: 'Pumpkin', bowlImgSrc: '../assets/img/PumpkinBowl.jpg', smoothieImgSrc: '../assets/img/PumpkinSmoothie.jpg' },
      {monthKey: 11, month: 'December', flavor: 'Cherry Pom Nutty', bowlImgSrc: '../assets/img/CherryPomBowl.jpg', smoothieImgSrc: '../assets/img/CherryPomSmoothie.jpg' }
    ]
    
    return {
      seasonalFlavors,
      movePrev() {
        var stream = document.querySelector('.gallery__stream');
        var items = document.querySelectorAll('.gallery__item');
        stream.insertBefore(items[items.length - 1], items[0]);
        items = document.querySelectorAll('.gallery__item');
      },
      moveNext() {
        var stream = document.querySelector('.gallery__stream');
        var items = document.querySelectorAll('.gallery__item');
        stream.appendChild(items[0]);
        items = document.querySelectorAll('.gallery__item');
      },
      // activeIndex: new Date().getMonth(),
      // methods: {
      //   prevSlide() {
      //     this.activeIndex = (this.activeIndex - 1 + this.seasonalFlavors.length) % this.seasonalFlavors.length;
      //   },
      //   nextSlide() {
      //     this.activeIndex = (this.activeIndex + 1) % this.seasonalFlavors.length;
      //   },
      // },
    }
  }
}
</script>

<style>
.seasonalSlide {
  height: 450px;
  width: 450px;
}

.blur {
  backdrop-filter: blur(24px) saturate(90%);
}

.seasonalRow {
  flex-wrap: nowrap !important;
}

.prevSlide {
  z-index: 3000;
  position: absolute;
  left: 0;
  top: 100rem;
}

.nextSlide {
  z-index: 3000;
  position: absolute;
  right: 0;
  top: 100rem;
}

.btnRow {
  height: 400px;
  align-items: center;
  display: flex;
}

.btn-slide {
  background-color: rgba(236, 236, 236, 0.619);
  /* height: 3rem;
  width: 3rem; */
  border-radius: 5px;
}

.btn-slide:hover {
  background-color: rgba(236, 236, 236, 0.932);
}

.gallery {
  width: 100%;
  height: 50vh;
  max-height: 50vh;
  overflow: hidden;
}

.gallery:before,
.gallery:after {
  display: block;
  content: "";
  position: absolute;
  /* top: 0; */
  width: 20%;
  height: 59%;
  z-index: 3;
}

.gallery:before {
  left: 0;
  background:  linear-gradient(to right, #fffaf3 0%, rgba(0,0,0,0) 100%);
}

.gallery:after {
  right: 0;
  background:  linear-gradient(to left, #fffaf3 0%, rgba(0,0,0,0) 100%);
}

.gallery__stream {
  /* position: relative;
  top: 50%;
  transform: translateY(-50%);
  width: 100%;
  height: 100%; */
}

.gallery__item {
  position: absolute;
  width: 50%;
  height: 100%;
  transition: 1s all ease;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  border-radius: 5px;
}

.gallery__item:nth-child(1) {
  left: 0;
  z-index: 1;
  transform: translateX(-100%) scale(.8);
}

.gallery__item:nth-child(2) {
  left: 0;
  z-index: 2;
  transform: translateX(-50%) scale(.8);
}

.gallery__item:nth-child(3) {
  left: 50%;
  z-index: 4;
  transform: translateX(-50%) scale(1);
}

.gallery__item:nth-child(4) {
  left: 100%;
  z-index: 2;
  transform: translateX(-50%) scale(.8);
}

.gallery__item:nth-child(n+5) {
  left: 100%;
}

.round-start {
  border-top-left-radius: 15px;
  border-bottom-left-radius: 15px;
}

.round-end {
  border-top-right-radius: 15px;
  border-bottom-right-radius: 15px;
}


.bg-FebruaryBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-FebruarySmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-MarchBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-MarchSmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-AprilBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-AprilSmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-MayBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-MaySmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-JuneBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-JuneSmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-JulyBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-JulySmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-AugustBowl {
  background-image: url('../assets/img/DragonBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-AugustSmoothie {
  background-image: url('../assets/img/DragonSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-SeptemberBowl {
  background-image: url('../assets/img/AppleFestBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-SeptemberSmoothie {
  background-image: url('../assets/img/AppleSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-OctoberBowl {
  background-image: url('../assets/img/AppleFestBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-OctoberSmoothie {
  background-image: url('../assets/img/AppleSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-NovemberBowl {
  background-image: url('../assets/img/PumpkinBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-NovemberSmoothie {
  background-image: url('../assets/img/PumpkinSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

.bg-DecemberBowl {
  background-image: url('../assets/img/CherryPomBowl.jpg');
  background-size: cover;
  background-position: center;
}

.bg-DecemberSmoothie {
  background-image: url('../assets/img/CherryPomSmoothie.jpg');
  background-size: cover;
  background-position: center;
}

</style>