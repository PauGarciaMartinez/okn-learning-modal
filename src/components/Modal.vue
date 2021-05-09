<template>
  <div class="backdrop">
    <div class="modal">
      <h2 class="title">{{ title }}</h2>
      <Input />
    </div>
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
  filter: blur(2px);
  z-index: 10;
}

.modal {
  background-color: white;
  height: 90%;
  width: 60%;
  max-width: 1200px;
  margin: 0 auto;
  border: 1px solid black;
  z-index: 2;
}

</style>