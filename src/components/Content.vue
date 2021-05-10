<template>

  <div v-for="item in content" :key="item">
    
    <!-- DELIVERY -->
    <div v-if="item.value.type">
      <div>
        <h5>{{ item.value.version }}</h5>
        <p class="delivery-name">{{ item.value.name }}</p>
        <p>
          {{ item.value.type }} 
          {{ item.value.size }} - 
          {{ item.value.date }}
        </p>
      </div>
      <div>
        <a :href="item.value.url">
          <i class="fas fa-cloud-download-alt"></i>
        </a>
      </div>
    </div>

    <!-- MESSAGE -->
    <div v-else>    
      <div v-if="item.value.author === 'student'" class="messages-wrapper">
        <div class="message-container">
          <p>{{ item.value.content }}</p>
          <small>{{ item.value.date }}</small>
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
          <p>{{ item.value.content }}</p>
          <small>{{ item.value.date }}</small>
        </div>
      </div>
    </div>

  </div>

</template>

<script>
import { Message } from '@/models/message.js'
import { Delivery } from '@/models/delivery.js'
import { ref } from 'vue'

export default {
  name: 'Content',
  setup() {
    let content = ref([])

    const message1 = ref(new Message('Buenas tardes, acabo de subir el primer archivo con el primer caso práctico, espero revisión.', '28 dic 2018/14:45', 'student'))

    const message2 = ref(new Message('¡Gran trabajo Pau! Pero creo que deberías revisar el punto 3. Intenta añadir un poco más de contexto y un apartado final de conclusiones personales.', '29 dic 2018/10:11', 'teacher'))
    
    const message3 = ref(new Message('Realizados los cambios según feedback.', '30 dic 2018/8:22', 'student'))

    const message4 = ref(new Message('Perfecto, excelente trabajo.', '30 dic 2018/15:25', 'teacher'))

    const delivery1 = ref(new Delivery('VERSIÓN 1', 'Título del archivo a subir 1.pdf', 'Documento/PDF', '(3.8 MB)', '28 dic 2018/14:45', 'url'))

    const delivery2 = ref(new Delivery('VERSIÓN 2', 'Título del archivo a subir 2.pdf', 'Documento/PDF', '(4.8 MB)', '30 dic 2018/8:22', 'url'))

    content.value.push(delivery1, message1, message2, delivery2, message3, message4)

    return { content }
  }
}
</script>

<style>

</style>