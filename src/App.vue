<template>
  <div class="site-container">  
    <About @toggle="toggleRSVP"></About>
    <Main></Main>
    <RSVP @sent="toggleRSVP" :state="rsvpState"></RSVP>
  </div>  
</template>

<script>
  import Main from '@/views/Main';
  import About from '@/views/About';
  import RSVP from '@/views/RSVP.vue';

  export default {
  
    components: { Main, About, RSVP },
    props: [],
    data() {
      return {
        rsvpState: false
      }
    },
    methods: {
        toggleRSVP() {
            this.rsvpState = !this.rsvpState;
        }
    }
  }
</script>

<style>

  @font-face {
    font-family: Reader;
    src: url('~@/assets/Reader-Regular.otf');
  }

  @font-face {
    font-family: Maison Neue;
    src: url('~@/assets/MaisonNeue-Book.ttf');
  }

  * {
    box-sizing: border-box;
    text-decoration: none;
  }

  a {
    text-decoration: none;
    color: black;
  }
  
  html{

    min-height: 100%;
    width: 100%;
    height: 100%;
    background-color: #000000;
  }
    
  body {
    width: 100%;
    min-height: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
    background-color: #000000;

  }

  .site-container {
    position: relative;
    width: 100%;
    min-height: 100%;
    height: 100%;
    overflow-x: hidden;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
    background-color: lightgrey;
  }

  @media (min-width: 320px) and (max-width: 425px)  {
    .site-container {
      scroll-snap-type: none;
    }
  }

</style>