<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal
      :header="header"
      :text="text"
      theme="sale"
      @click.self="toggleModal"
    />
  </div>
  <button @click="toggleModal">open modal</button>
  <input type="text" ref="name" />
  <!-- <button @click="handleClick">Click me</button> -->
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first Vue App :)",
      header: "Sign up for the Giveaway!",
      text: "Grab your ninja swag for half price!",
      showModal: false,
    };
  },
  methods: {
    /* handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    }, */
    toggleModal() {
      this.showModal = !this.showModal;
      console.log("close");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline;
  padding-bottom: 20px;
}
</style>
