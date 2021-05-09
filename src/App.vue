<template>

  <header>
    <img src="@/assets/logo-okn.png" alt="OKN Learning logo">
    <button class="modal-btn" @click="toggleModal">Chat</button>
  </header>

  <Modal v-if="visible" />

</template>

<script>
import Modal from '@/components/Modal'
import { ref } from 'vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  setup() {
    let visible = ref(false)

    const toggleModal = () => {
      visible.value = !visible.value
    }

    return { visible, toggleModal }
  }
}
</script>

<style>
/* GLOBAL STYLING */ 
body {
  margin: 0;
  height: 100vh;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin-top: -4rem;
}

.modal-btn {
  background-color: rgb(56, 190, 231);
  color: white;
  font-size: 1rem;
  font-weight: 600;
  width: 5rem;
  height: 2rem;
  margin-right: 3rem;
  border: 0px solid black;
  border-radius: 0.3rem;
  cursor: pointer;
}

.modal-btn:hover {
  
}

</style>
