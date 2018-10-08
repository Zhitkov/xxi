<template>
		<div id="WebGL-output"></div>
</template>

<script scop>
import * as THREE from 'three'

export default {

  name: 'City',

  data () {
    return {

    }
  },
  mounted(){
  		const OrbitControls = require('three-orbitcontrols');

	  var scene = new THREE.Scene();
	  var camera = new THREE.PerspectiveCamera(45, window.innerWidth /     window.innerHeight, 0.1, 1000),controls;

	  	camera.position.set( 140, 140, 140 );
	    controls = new OrbitControls( camera );
	    controls.enableZoom = false;
	    controls.enableKeys = true;
	    controls.minDistance = 70;
	    controls.maxDistance = 140;

	  var renderer = new THREE.WebGLRenderer();

	  renderer.setSize(window.innerWidth, window.innerHeight);
	  
	  renderer.setClearColor(0x000000); 
	  scene.fog = new THREE.FogExp2( 0x000000, 0.0085 );
	  
	  var groundGeo = new THREE.PlaneGeometry(400,400,4,4);
	  var groundMat = new THREE.MeshPhongMaterial({color:0x244876});
	 
	  var ground = new THREE.Mesh(groundGeo,groundMat);
	  scene.add(ground);
	  ground.position.x = 140; 
	  ground.position.y = 0; 
	  ground.position.z = -150; 
	  ground.rotation.x = -1.55;
	  
	  camera.position.x = 0; 
	  camera.position.y = 25; 
	  camera.position.z = 0; 
	  
	  camera.rotation.y = -0.785398163;
	  camera.rotation.z = -0.280;
	  camera.rotation.x = -0.400;
	  

	  var monolith = [];
	  var monolithGeo = new THREE.CubeGeometry( 4,4,4); 
	  var monolithMat = new THREE.MeshPhongMaterial( {color: 0x244876}); 
	  monolithMat.shininess = 100;
	  var monolithRow = [];
	  var rowZ = 0;
	  
	  for (var r=0; r<100; r++){
	    rowZ -= 10;
	    
	    for (var i=0; i<35; i++){
	      monolith[i] = new THREE.Mesh(new THREE.CubeGeometry(4, 4, 4), new THREE.MeshBasicMaterial({
	        wireframe: true,
	        color: '#c1ffff'
	      }));
	      monolith[i].position.x = i*10; 
	      monolith[i].position.y = 0; 
	      monolith[i].position.z = rowZ; 
	    
	      var rand = Math.ceil(Math.random()*10);
	      monolith[i].scale.y = rand;
	      scene.add(monolith[i]); 
	    }
	  }
	  
	  
	  render();
	  
	  function render(){
	    requestAnimationFrame(render);
	    camera.position.z -= 0.1;
	    camera.position.x += 0.1;  
	    // controls.update();
	    renderer.render(scene, camera);
	  };
	  document.body.appendChild( renderer.domElement );
	  
  }
}
</script>

<style lang="stylus" scoped>
	
</style>