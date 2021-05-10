<template>

  <form>
    <input 
      type="text" 
      class="input-msg"
      v-model="message">
    <button class="input-btn" @click.prevent="sendMessage">
      <i class="fas fa-paper-plane"></i>
    </button>
  </form>
  
</template>

<script>
import { Message } from '@/models/message.js'
import { ref } from 'vue'

export default {
  name: 'Input',
  emits: ['send-message'],
  setup(props, { emit }) {
    let message = ref('')

    const sendMessage = () => {
      const newMessage = ref(new Message(message.value, Date, 'student'))
      emit('send-message', newMessage)
    }

    return { message, sendMessage }
  }
}
</script>

<style>
form {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  margin-top: 2rem;
}

.input-msg {
  width: 95%;
  height: 1.5rem;
  border: 2px solid rgba(128, 128, 128, 0.144);
  border-radius: 1rem;
  background-color: rgb(248, 248, 248);
  outline: none;
  text-indent: 1rem;
}

.input-btn {
  width: 2.5rem;
  height: 1.8rem;
  border: 0px solid black;
  border-radius: 0.5rem;
  background-color: rgb(56, 190, 231);
  outline: none;
  transition: 0.2s;
}

.input-btn:hover {
  background-color: rgb(9, 96, 122);
  cursor: pointer;
  transition: 0.2s;
}

.fa-paper-plane {
  font-size: 1.1rem;
  color: white;
}
</style>