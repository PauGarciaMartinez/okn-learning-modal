<template>
  <div class="backdrop"></div>
  <div class="modal">
    <h2 class="title">{{ title }}</h2>
    <Input />
  </div>
</template>

<script>
import Input from '@/components/Input'
import Message from '@/components/Input'
import Delivery from '@/components/Input'
import { ref } from 'vue'

export default {
  name: 'Modal',
  components: {
    Input,
    Message, 
    Delivery
  },
  setup() {
    let title = ref('Comentarios')

    return { title }
  }
}
</script>

<style>
.backdrop {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(56, 190, 231, 0.068);
  backdrop-filter: blur(4px);
}

.modal {
  position: relative;
  background-color: white;
  height: 90%;
  width: 60%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  border-radius: 0.5rem;
  box-shadow: 5px 5px 10px rgb(218, 218, 218);
}

</style>