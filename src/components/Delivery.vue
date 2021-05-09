<template>

  <div class="delivery-wrapper">
    <div class="info-container">
      <h4>{{ delivery1.version }}</h4>
      <p>{{ delivery1.name }}</p>
      <p>{{ delivery1.type }} {{ delivery1.size }} {{ delivery1.date }}</p>
    </div>
    <div class="download-container">
      
    </div>
  </div>

</template>

<script>
import { Delivery } from '@/models/delivery.js'
import { ref } from 'vue'

export default {
  name: 'Delivery',
  setup() {
    let delivery1 = ref(new Delivery('VERSIÓN 1', 'Título del archivo a subir 1', 'Documento/PDF', '(3.8 MB)', '28 dic 2018/14:45', 'url'))

    let delivery2 = ref()
    
    return { delivery1 }
  }
}
</script>

<style>

</style>