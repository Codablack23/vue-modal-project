<template>
  <div id="app">
    <h1>My Vue Modal</h1>
    <teleport to=".modals" class="modal-container" v-if="showModal">
      <Modal :theme="theme" @close="ToggleModal">
        <h3>{{ title }}</h3>
        <h5>{{ text }}</h5>
        <template v-slot:links>
          <a href="#">Sign Up Now</a>
          <a href="#">More Info</a>
        </template>
      </Modal>
    </teleport>
    <button @click="ToggleModal" class="toggleModalBtn">Toggle Modal</button>
  </div>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      title: 'Sign Up For A Giveaway',
      text: 'Get 50% Discount For Every Purcahse',
      theme: 'sale',
      showModal: false,
    };
  },
  methods: {
    ToggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app h1 {
  color: grey;
}
</style>
