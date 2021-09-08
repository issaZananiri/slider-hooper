<template>
<div class="card-wrapper">
  <div class='card1'>


      <div class="card-header1">חבילות אינטרנט</div>

    
      <span class="card-span">המהירים- ואתם נהנים מחויית גלישה</span>
       
      <span class="card-span">מצטרפת למהפכת הסיבים </span>
 
      <span class="card-span">עוצמתית וזורמתית מתמיד</span>

<div>
  <hooper class="slideA"  ltr="true" group="group1" :itemsToShow="5"  :progress="true" :autoPlay="true" :playSpeed="3000" :centerMode="true">
    
  <slide>
    slide 1
    <span>this is a test</span>
  </slide>
  <slide>
    slide 2 t
  </slide>
  <slide>
    slide 3
  </slide>
  <slide>
    slide 4
  </slide>
  <slide>
    slide 5
  </slide>
  <slide>
    slide 6
  </slide>

  <hooper-navigation slot="hooper-addons"></hooper-navigation>
  <hooper-pagination slot="hooper-addons"></hooper-pagination>
</hooper>
  <hooper  class="slideB" style="width:728px; padding-left: 82px;" group="group1" :centerMode="true" :itemsToShow="1.36"  >
  <slide  style="padding-right:45px;">
    slide 1
    
  </slide>
  <slide style="padding-right:25px;">
    slide 2
  </slide >
  <slide style=" all: none;">
    slide 3 
    <i class="bi bi-check"></i>
    <span>hi</span>
  </slide>
  <slide style=" all: none;">
    slide 4
  </slide>
  <slide style=" all: none;">
    slide 5
  </slide>
  <slide style=" all: none;">
    slide 6
  </slide>
</hooper>

</div>
</div>
  </div>
</template>

<script>

import { Hooper, Slide,  Navigation as HooperPagination} from 'hooper';
import 'hooper/dist/hooper.css';

import '../style.css'





export default {
  components: {
    HooperPagination,
    Hooper,
    Slide
  },
 
  watch: {
    carouselData () {
      this.$refs.carousel.slideTo(this.carouselData);
    }
  },
  methods:{
    carouselButton(index){
      this.$refs.carousel.slideTo(index);
      this.activeLinkIndex = index
    },


    scrollTop(){
      this.$refs.carousel.slidePrev();
    },
    scrollBottom(){
      this.$refs.carousel.slideNext();
    },

    updateCarousel(payload) {
      this.myCarouselData = payload.currentSlide;
    },

  },
  data(){
    return{
      carouselData: 0,
      quantity: 1,
    
      activeLinkIndex: null,
  
      hooperSettings: {
              itemsToShow: 1,
              centerMode: true,
              infiniteScroll: true ,
              breakpoints: {
                1240:{
                  itemsToShow: 1,
                  vertical: true,
                },
                992: {
                  itemsToShow: 1,
                  vertical: true,
                },
                768:{
                  itemsToShow: 1,
                  vertical:true,
                },
                576:{
                 itemsToShow: 1,
                  vertical: true,
                },
                360:{
               itemsToShow: 1,
                  vertical: true,
                }
              }
            },
      mainHooperSettings:{
        infiniteScroll: false,
        centerMode: true,
        itemsToShow:1
      }
    }
  },
  mounted() {
    
    setTimeout(() => this.$refs.mainCarousel.updateWidth().bind(this), 50)
    
  },
};

</script>
