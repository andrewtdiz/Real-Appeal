<template>
  <div id="app" class="relative" >
    <Modal />
    <router-view />
  </div>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  components: {
    Modal,
  },
  computed: {
        showModal() {
            return this.$store.getters.getShowModal
        },
    },
  watch: {
    
    $route(to, from) {
      this.$store.commit('setActiveStage', 0)
      this.$store.commit('setprevStage', 0)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
