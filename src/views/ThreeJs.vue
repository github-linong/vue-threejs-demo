<template>
  <div class="threejs" >
    <div class="threejs-view" ref="threeView"></div>
  </div>
</template>
<style lang="scss" scoped>
  .threejs{
    // .threejs-view{
    //   width: 500px;height: 500px;
    // }
    :deep canvas { width: 100%; height: 100% }
  }
</style>
<script>
/* eslint-disable no-undef */
/* eslint-disable no-unused-vars */
export default {
  name: 'Home',
  components: {
  },
  mounted() {
    this.initThree();
  },
  methods: {
    initThree() {
      const el = this.$refs.threeView;
      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera(75,
        window.innerWidth / window.innerHeight, 0.1, 1000);
      const renderer = new THREE.WebGLRenderer();
      renderer.setSize(window.innerWidth, window.innerHeight);
      el.appendChild(renderer.domElement);

      const geometry = new THREE.BoxGeometry(1, 1, 1);
      const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
      const cube = new THREE.Mesh(geometry, material);
      scene.add(cube);

      camera.position.z = 5;

      function animate() {
        cube.rotation.x += 0.01;
        cube.rotation.y += 0.01;
        requestAnimationFrame(animate);
        renderer.render(scene, camera);
      }
      animate();
    },
  },
};
</script>
