<template>
  <section class="home-hero">
    <div class="rellax home-hero__name"  data-rellax-speed="-2">
      <div class="first-name-inner">ANDY</div>
    </div>
    <div class="rellax home-hero__name-last" data-rellax-speed="2" data-rellax-zindex="2">
      <div class="last-name-inner">
        SIPPLE
      </div>
    </div>
    <!-- <div class="home-hero__title">Full Stack Developer.</div>
    <div class="home-hero__who">
      <div class="who-text">
        I have a passion for code and a love for troubleshooting problems!
      </div>
    </div>
    <div class="rellax home-hero__year" data-rellax-speed="16">Born in the 80's. Raised in the 90's. Living in the now.</div> -->
  </section>
</template>
<script>
  import Rellax from 'Rellax';
  
  export default {
    mounted:function(){
      const rellax = new Rellax('.rellax', {
        speed: -1,
        center: false,
        wrapper: null,
        round: true,
        vertical: true,
        horizontal: false
      });
    }
  }
</script>
<style lang="scss">
  @import '~assets/scss/settings/variables';
  @import '~assets/scss/settings/mixins';
  @import url('https://fonts.googleapis.com/css?family=Ubuntu+Condensed');
  .home-hero {
    display: grid;
    grid-template-columns: repeat(8, var(--gridSize));
    grid-template-rows: repeat(10, var(--gridSize));
    grid-gap: 0px;
    width: 100%;
    max-width: var(--max-width);
    margin: auto;
    font-family: 'Ubuntu Condensed', sans-serif;

    &__name {
      @include responsive-font(5vw, 250px, 350px, 50px);
      @include text3d  (white, -2, 1, 1.3);
      display: flex;
      justify-content: flex-start;
      align-items: center;
      flex-direction: row;
      grid-column: 2/5;
      grid-row: 2;
      color: white;
      .first-name-inner {
        transform: perspective( 600px ) rotateY( 30deg );
      }
    }
 
    &__name-last {
      @include responsive-font(60vw, 150px, 350px, 60px);
      grid-column: 4;
      grid-row: 3;
      .last-name-inner {
        @include text3d  (white, -2, 1, 1.6);
        color: white;
        transform: perspective( 600px ) rotateY( 30deg );
      }
    }
    &__title {
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: white;
      background: #4cd137;
      background-size: 600% 600%; 
      grid-column: 7;
      grid-row: 4;
    }
    &__who {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      grid-column: 3/6;
      grid-row: 6/8;
      z-index: 100;
      padding: 40px;
      text-align: center;
      color: white;
      background: #000;
    }
    &__year {
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 40px;
      text-align: center;
      color: white;
      line-height: 1.5em;
      background: linear-gradient(270deg, #ff3f3f, #c04df9, #2bd1fc);
      animation: AnimationName 3s ease infinite;
      background-size: 600% 600%; 
      grid-column: 2;
      grid-row: 5;
    }
  }

@keyframes AnimationName { 
    0%{background-position:0% 86%}
    50%{background-position:100% 15%}
    100%{background-position:0% 86%}
}
</style>
