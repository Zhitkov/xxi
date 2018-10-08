<template>
  <div class="mainPage">
     <div class="logo">
      <h1 class="max">MAXXIMOV<h3 class="pro">Production</h3></h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  data () {
    return {
      
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
      @keyframes rainbow-shift {
        25% {
        text-shadow: 
             0px 1px 1px #ddd,
             0px 2px 1px #d6d6d6,
             0px 3px 1px #ccc,
             0px 4px 1px #c5c5c5,
             0px 5px 1px #c1c1c1,
             0px 6px 1px #bbb,
             0px 7px 1px #777,
             0px 8px 3px rgba(100, 100, 100, 0.4),
             0px 9px 5px rgba(100, 100, 100, 0.1),
             0px 10px 7px rgba(100, 100, 100, 0.15),
             0px 11px 9px rgba(100, 100, 100, 0.2),
             0px 12px 11px rgba(100, 100, 100, 0.25),
             0px 13px 15px rgba(100, 100, 100, 0.3);
        }
        // 50% {
        // text-shadow: 
        //      0px 1px 1px #ddd,
        //      0px 2px 2px #d6d6d6,
        //      0px 3px 3px #ccc,
        //      0px 4px 4px #c5c5c5,
        //      0px 5px 5px #c1c1c1,
        //      0px 6px 6px #bbb,
        //      0px 7px 1px #777,
        //      0px 8px 3px rgba(100, 100, 100, 0.4),
        //      0px 9px 5px rgba(100, 100, 100, 0.1),
        //      0px 10px 7px rgba(100, 100, 100, 0.15),
        //      0px 11px 9px rgba(100, 100, 100, 0.2),
        //      0px 12px 11px rgba(100, 100, 100, 0.25),
        //      0px 13px 15px rgba(100, 100, 100, 0.3);

        // }
        // 75% {
        // text-shadow: 
        //      0px 1px 1px #ddd,
        //      0px 2px 1px #d6d6d6,
        //      0px 3px 1px #ccc,
        //      0px 4px 1px #c5c5c5,
        //      0px 5px 1px #c1c1c1,
        //      0px 6px 1px #bbb,
        //      0px 7px 1px #777,
        //      0px 8px 3px rgba(100, 100, 100, 0.4),
        //      0px 9px 5px rgba(100, 100, 100, 0.1),
        //      0px 10px 7px rgba(100, 100, 100, 0.15),
        //      0px 11px 9px rgba(100, 100, 100, 0.2),
        //      0px 12px 11px rgba(100, 100, 100, 0.25),
        //      0px 13px 15px rgba(100, 100, 100, 0.3);

        // }
        100% {
        text-shadow: 
             0px 1px 2px #ddd,
             0px 2px 4px #d6d6d6,
             0px 3px 6px #ccc,
             0px 4px 7px #c5c5c5,
             0px 5px 23px #c1c1c1,
             0px 6px 4px #bbb,
             0px 7px 65px #777,
             0px 8px 32px rgba(100, 100, 100, 0.4),
             0px 9px 34px rgba(100, 100, 100, 0.1),
             0px 10px 134px rgba(100, 100, 100, 0.15),
             0px 11px 40px rgba(100, 100, 100, 0.2),
             0px 12px 11px rgba(100, 100, 100, 0.25),
             0px 13px 15px rgba(100, 100, 100, 0.3);
        }
    }



      .mainPage
        background-color black
        width 100vw
        height 100vh
        display grid
        grid-template-columns repeat(3, 1fr)
      #myCanvas
          height 100%
          width 100%
          grid-row 3/2
          grid-column 1/4
      .logo
        grid-column 2
        grid-row 2
        color white
        text-align center
        z-index 1
        .max
          font-family: 'Russo One', sans-serif;
          font-size 72px
          text-shadow: 0px 1px 1px #ddd,
                     0px 2px 1px #d6d6d6,
                     0px 3px 1px #ccc,
                     0px 4px 1px #c5c5c5,
                     0px 5px 1px #c1c1c1,
                     0px 6px 1px #bbb,
                     0px 7px 1px #777,
                     0px 8px 3px rgba(100, 100, 100, 0.4),
                     0px 9px 5px rgba(100, 100, 100, 0.1),
                     0px 10px 7px rgba(100, 100, 100, 0.15),
                     0px 11px 9px rgba(100, 100, 100, 0.2),
                     0px 12px 11px rgba(100, 100, 100, 0.25),
                     0px 13px 15px rgba(100, 100, 100, 0.3);
          transition:all .8s ease-in-out;  
          -o-transition:all .8s ease-in-out;  
          -moz-transition:all .8s ease-in-out;  
          -webkit-transition:all .8s ease-in-out;
          // &:hover
          //   .max
          //     font-size 100px
          animation: rainbow-shift 7s ease-in-out infinite alternate
        .pro
          font-size 50px
          margin-block-start: .2em;
          margin-block-end: 0;

        @media screen and (max-width:768px) 
          .max
            font-size 70px 
          .pro
            font-size 55px
        

        @media screen and (max-width:480px) 
          .max
            font-size 47px 
          .pro
            font-size 40px
          
</style>
