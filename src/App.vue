<template>
  
  <header>
    <img src="@/assets/logo-okn.png" alt="OKN Learning logo">
    <button class="modal-btn" @click="toggleModal">
      <i class="fas fa-comments"></i>
    </button>
  </header>

  <Modal v-show="visible" @close-modal="visible = $event" />

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
    let visible = ref(true)

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
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  margin-top: -4rem;
}

/* BUTTON */
.modal-btn {
  font-size: 1rem;
  font-weight: 600;
  width: 5rem;
  height: 2.5rem;
  margin-right: 3rem;
  background-color: rgb(56, 190, 231);
  color: white;
  border: 0px solid black;
  border-radius: 0.3rem;
  outline: none;
  cursor: pointer;
  transition: 0.3s;
}

.modal-btn:hover {
  background-color: rgb(9, 96, 122);
  transition: 0.2s;
}

.fa-comments {
  font-size: 1.6rem;
}

</style>
