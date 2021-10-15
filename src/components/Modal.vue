<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme == 'sale' }">
      <slot></slot>
      <div class="action">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['theme'],
  methods: {
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}
.backdrop .modal {
  max-width: 400px;
  padding: 40px;
  background: white;
  margin: 50px auto;
  border-radius: 10px;
}
.backdrop .sale {
  background: crimson;
  color: white;
}
.backdrop .sale .action a {
  color: white;
  text-decoration: none;
  padding: 10px;
  border-radius: 10px;
  border: 1px solid white;
  margin: 10px;
}
.backdrop .action a {
  color: grey;
  text-decoration: none;
  padding: 10px;
  border-radius: 10px;
  border: 1px solid lightgrey;
  margin: 10px;
}
</style>
