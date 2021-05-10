<template>
  <div>
    <div class="backdrop" @click="closeModal"></div>
    <div class="modal">
      <div class="close-container">
        <i class="fas fa-times" @click="closeModal"></i>
      </div>
      <h2 class="title">{{ title }}</h2>

      <div class="content-container">
        <Content :message="message.value" />
      </div>

      <Input @send-message="message.value = $event" />

    </div>
  </div>


</template>

<script>
import Input from '@/components/Input'
import Content from '@/components/Content'
import { ref } from 'vue'

export default {
  name: 'Modal',
  emits: ['close-modal'],
  components: {
    Content,
    Input
  },
  setup(props, { emit }) {
    let title = ref('Comentarios')

    let message = ref({})

    const closeModal = () => {
      emit('close-modal', false)
    }

    return { title, closeModal, message }
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
  width: 70%;
  max-width: 1000px;
  margin: 0 auto;
  margin-top: -1.5rem;
  padding: 2rem;
  border-radius: 0.5rem;
  box-shadow: 5px 5px 10px rgb(218, 218, 218);
}

.close-container {
  display: flex;
  justify-content: flex-end;
  height: 0.5rem;
}

.fa-times {
  font-size: 1.5rem;
  color: rgb(56, 190, 231);
  transition: 0.1s;
}

.fa-times:hover {
  cursor: pointer;
  transform: scale(1.3);
  transition: 0.1s;
}

.title {
  padding-bottom: 1rem;
  border-bottom: 2px solid black;
}

.content-container {
  max-height: 500px;
  overflow-y: scroll;
}

</style>