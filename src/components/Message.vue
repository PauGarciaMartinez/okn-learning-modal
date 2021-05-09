<template>
  <div class="messages-wrapper" v-for="msg in messages" :key="msg">
    <div class="message-container">
      <p>{{ msg.value.content }}</p>
      <small>{{ msg.value.date }}</small>
    </div>
  </div>
  
</template>

<script>
import { Message } from '@/models/message.js'
import { ref } from 'vue'

export default {
  name: 'Message',
  setup() {
    let messages = ref([])

    const message1 = ref(new Message('Buenas tardes, acabo de subir el primer archivo con el primer caso práctico, espero revisión.', '28 dic 2018/14:45'))

    const message2 = ref(new Message('¡Gran trabajo Pau! Pero creo que deberías revisar el punto 3. Intenta añadir un poco más de contexto y un apartado final de conclusiones personales.', '29 dic 2018/10:11'))
    
    const message3 = ref(new Message('Realizados los cambios según feedback.', '30 dic 2018/8:22'))

    const message4 = ref(new Message('Perfecto, excelente trabajo.', '30 dic 2018/15:25'))

    messages.value.push(message1, message2, message3, message4)

    return { messages }
  }
}
</script>

<style>
.messages-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
  margin: 1rem 0;
}
.message-container {
  text-align: right;
  background-color: rgb(56, 190, 231);
  padding: 0.5rem 1rem;
  max-width: 70%;
  border-radius: 0.5rem;
  color: white;
}
</style>