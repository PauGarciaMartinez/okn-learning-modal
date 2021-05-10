<template>

  <div v-for="item in content" :key="item">
    
    <!-- DELIVERY -->
    <div v-if="item.value.type">
      <ChatDelivery>
        <template v-slot:version>{{ item.value.version }}</template>
        <template v-slot:name>{{ item.value.name }}</template>
        <template v-slot:info>
          {{ item.value.type }} 
          {{ item.value.size }} - 
          {{ item.value.date }}
        </template>
        <template v-slot:download>
          <a :href="item.value.url">
            <i class="fas fa-cloud-download-alt"></i>
          </a>
        </template>
      </ChatDelivery>
    </div>

    <!-- MESSAGE -->
    <div v-else>
      <ChatMessage :item="item.value">
          <template v-slot:content>{{ item.value.content }}</template>
          <template v-slot:date>{{ item.value.date }}</template>
      </ChatMessage>    
    </div>

  </div>

{{ message }}

</template>

<script>
import ChatMessage from '@/components/ChatMessage'
import ChatDelivery from '@/components/ChatDelivery'
import { Message } from '@/models/message.js'
import { Delivery } from '@/models/delivery.js'
import { watch, ref, onUpdated, watchEffect } from 'vue'

export default {
  name: 'Content',
  components: {
    ChatMessage,
    ChatDelivery
  },
  props: ['message'],
  setup(props) {
    let content = ref([])

    const message1 = ref(new Message('Buenas tardes, acabo de subir el primer archivo con el primer caso práctico, espero revisión.', '28 dic 2018/14:45', 'student'))

    const message2 = ref(new Message('¡Gran trabajo Pau! Pero creo que deberías revisar el punto 3. Intenta añadir un poco más de contexto y un apartado final de conclusiones personales.', '29 dic 2018/10:11', 'teacher'))
    
    const message3 = ref(new Message('Realizados los cambios según feedback.', '30 dic 2018/8:22', 'student'))

    const message4 = ref(new Message('Perfecto, excelente trabajo.', '30 dic 2018/15:25', 'teacher'))

    const delivery1 = ref(new Delivery('VERSIÓN 1', 'Título del archivo a subir 1.pdf', 'Documento/PDF', '(3.8 MB)', '28 dic 2018/14:45', 'url'))

    const delivery2 = ref(new Delivery('VERSIÓN 2', 'Título del archivo a subir 2.pdf', 'Documento/PDF', '(4.8 MB)', '30 dic 2018/8:22', 'url'))

    content.value.push(delivery1, message1, message2, delivery2, message3, message4)

    let newMessage = ref(props.message)

    watch(newMessage, () => {
      content.value.push(props.message)
    })


    /* onUpdated(() => {
      content.value.push(props.message)
    })  */

    /* console.log(props)

    console.log(newMessage.value)

    watch(newMessage, () => {
      content.value.push(newMessage.value)
    }) */

    return { content }
  }
}
</script>

<style>

</style>