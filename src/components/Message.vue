<template>

  <div v-for="msg in messages" :key="msg">
    <div v-if="msg.value.author === 'student'" class="messages-wrapper">
      <div class="message-container">
        <p>{{ msg.value.content }}</p>
        <small>{{ msg.value.date }}</small>
      </div>
      <div class="thumbnail">
        <img src="@/assets/student-profile.jpeg" alt="Student's profile photo">
      </div>
    </div>
    <div v-else class="messages-wrapper2">
      <div class="thumbnail">
        <img src="@/assets/teacher-profile.jpeg" alt="Teacher's profile photo">
      </div>
      <div class="message-container2">
        <p>{{ msg.value.content }}</p>
        <small>{{ msg.value.date }}</small>
      </div>
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

    const message1 = ref(new Message('Buenas tardes, acabo de subir el primer archivo con el primer caso práctico, espero revisión.', '28 dic 2018/14:45', 'student'))

    const message2 = ref(new Message('¡Gran trabajo Pau! Pero creo que deberías revisar el punto 3. Intenta añadir un poco más de contexto y un apartado final de conclusiones personales.', '29 dic 2018/10:11', 'teacher'))
    
    const message3 = ref(new Message('Realizados los cambios según feedback.', '30 dic 2018/8:22', 'student'))

    const message4 = ref(new Message('Perfecto, excelente trabajo.', '30 dic 2018/15:25', 'teacher'))

    messages.value.push(message1, message2, message3, message4)

    return { messages }
  }
}
</script>

<style>
/* STUDENT MESSAGES */
.messages-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  gap: 1rem;
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

.thumbnail {
  max-width: 50px;
}

.thumbnail img {
  max-height: 30px;
  max-width: 35px;
  border-radius: 0.5rem;
}

/* TEACHER MESSAGES */
.messages-wrapper2 {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 1rem;
  margin: 1rem 0;
}
.message-container2 {
  text-align: left;
  background-color: rgb(246, 246, 246);
  padding: 0.5rem 1rem;
  max-width: 70%;
  border-radius: 0.5rem;
}
</style>