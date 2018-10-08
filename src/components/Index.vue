<template>
	<div>
		<MainPage/>
    <Fog/>
		<Products/>
    <div class="flip">
      <Fog2/>
    </div>
    <div class="blank"></div>
      <City class="city"/>
	</div>
</template>

<script>
import MainPage from './MainPage.vue'
import Products from './layouts/Products.vue'
import Fog from './layouts/Fog'
import Fog2 from './layouts/Fog2'
import City from './layouts/City'


export default {
  name: 'Index',
  components:{
    MainPage,
    Products,
    Fog,
    City,
    Fog2
  },
  data () {
    return {

    }
  },
}
</script>

<style lang="stylus" scoped>
  #myCanvas
    position absolute
    width 100vw
    height 200vh
    top 0vh
    // filter: blur(100px);
  .flip
    position absolute
    width 100vw
    height 200vh
    top 200vh 
    transform scale(-1)
  .blank
    width 100vw
    height 100vh
</style>
