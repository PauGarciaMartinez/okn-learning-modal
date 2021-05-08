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
  filter: blur(2);
}

.modal {
  background-color: white;
  width: 1200px;
}

</style>