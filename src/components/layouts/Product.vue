<template>
	<div class="products">
		<div v-for="product in products">
			<div id="container" class="product-img">
				<img id="inner" :style="`background-image:url(${product.src})`">
			</div>
		</div>
	</div>
</template>

<script>
export default {
  name: 'MainPage',
  data () {
    return {
    	products:[
    		{
    			id: 1,
    			name: "111111",
    			desk: "Russo means Russian. It seems strange that in a such font there is no snow, vodka or bears. What I wanted to show is that Russian culture is quite varied and modern. In Russia, too, some people love good fonts and typography. Russo One is designed for headlines and logotypes. It is simple and original, stylish and casual.",
    			src:"./../../../static/images/pr1.png",
    			size:"",
    			color:"",
    			type:"",
    			amount:false
    		},
    		{
    			id: 2,
    			name: "2222",
    			desk: "Russo means Russian. It seems strange that in a such font there is no snow,quite varied and modern. In Russia, too, some people love good fonts and typography. Russo One is designed for headlines and logotypes. It is simple and original, stylish and casual.",
    			src:"./../../../static/images/pr2.png",
    			size:"",
    			color:"",
    			type:"",
    			amount:false
    		},
    		{
    			id: 3,
    			name: "33333",
    			desk: "Russo means Russian. It seems strange that in a such font there is no snow, vodka or bears. What I wanted to show is that Russian culture is quite love good fonts and typography. Russo One is designed for headlines and logotypes. It is simple and original, stylish and casual.",
    			src:"./../../../static/images/pr3.png",
    			size:"",
    			color:"",
    			type:"",
    			amount:false
    		}
    	]
    }
  },
mounted(){
		  // Init
		  var container = document.getElementById("container"),
		    inner = document.getElementById("inner");

		  // Mouse
		  var mouse = {
		    _x: 0,
		    _y: 0,
		    x: 0,
		    y: 0,
		    updatePosition: function(event) {
		      var e = event || window.event;
		      this.x = e.clientX - this._x;
		      this.y = (e.clientY - this._y) * -1;
		    },
		    setOrigin: function(e) {
		      this._x = e.offsetLeft + Math.floor(e.offsetWidth / 2);
		      this._y = e.offsetTop + Math.floor(e.offsetHeight / 2);
		    },
		    show: function() {
		      return "(" + this.x + ", " + this.y + ")";
		    }
		  };

		  // Track the mouse position relative to the center of the container.
		  mouse.setOrigin(container);

		  //-----------------------------------------

		  var counter = 0;
		  var updateRate = 10;
		  var isTimeToUpdate = function() {
		    return counter++ % updateRate === 0;
		  };

		  //-----------------------------------------

		  var onMouseEnterHandler = function(event) {
		    update(event);
		  };

		  var onMouseLeaveHandler = function() {
		    inner.style = "";
		  };

		  var onMouseMoveHandler = function(event) {
		    if (isTimeToUpdate()) {
		      update(event);
		    }
		  };

		  //-----------------------------------------

		  var update = function(event) {
		    mouse.updatePosition(event);
		    updateTransformStyle(
		      (mouse.y / inner.offsetHeight / 2).toFixed(2),
		      (mouse.x / inner.offsetWidth / 2).toFixed(2)
		    );
		  };

		  var updateTransformStyle = function(x, y) {
		    var style = "rotateX(" + x + "deg) rotateY(" + y + "deg)";
		    inner.style.transform = style;
		    inner.style.webkitTransform = style;
		    inner.style.mozTransform = style;
		    inner.style.msTransform = style;
		    inner.style.oTransform = style;
		  };

		  //-----------------------------------------

		  container.onmouseenter = onMouseEnterHandler;
		  container.onmouseleave = onMouseLeaveHandler;
		  container.onmousemove = onMouseMoveHandler;
	}
}
</script>

<style lang="stylus" scoped>
	.products
		width 100vw
		height 100vh
		background-color #CECECE
		background url("../../../static/images/fog.gif") repeat
		background-size 100vw 100vh
		background-opacity .5
		img
			width 30vw
			height 40vh
	#container 
		perspective: 25px;

	#inner 
		// box-shadow: 2px 2px 50px rgba(0, 0, 0, 0.2);
		transition: transform 0.5s;
		-webkit-transition: transform 0.5s;
		-moz-transition: transform 0.5s;
		-o-transition: transform 0.5s;

		
</style>