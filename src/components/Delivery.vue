<template>

  <div class="delivery-wrapper" v-for="delivery in deliveries" :key="delivery">
    <div>
      <h5>{{ delivery.value.version }}</h5>
      <p class="delivery-name">{{ delivery.value.name }}</p>
      <p>
        {{ delivery.value.type }} 
        {{ delivery.value.size }} - 
        {{ delivery.value.date }}
      </p>
    </div>
    <div>
      <a :href="delivery.value.url">
        <i class="fas fa-cloud-download-alt"></i>
      </a>
    </div>
  </div>

</template>

<script>
import { Delivery } from '@/models/delivery.js'
import { ref } from 'vue'

export default {
  name: 'Delivery',
  setup() {
    let deliveries = ref([])

    let delivery1 = ref(new Delivery('VERSIÓN 1', 'Título del archivo a subir 1.pdf', 'Documento/PDF', '(3.8 MB)', '28 dic 2018/14:45', 'url'))

    let delivery2 = ref(new Delivery('VERSIÓN 2', 'Título del archivo a subir 2.pdf', 'Documento/PDF', '(4.8 MB)', '30 dic 2018/8:22', 'url'))

    deliveries.value.push(delivery1, delivery2)
    
    return { delivery1, delivery2, deliveries }
  }
}
</script>

<style>
.delivery-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  text-align: left;
  line-height: 1;
  margin: 0 1rem;
  border-bottom: 1px solid grey;
}

.delivery-name {
  font-weight: 600;
  color: rgb(56, 190, 231);
}

.fa-cloud-download-alt {
  font-size: 1.8rem;
  color: rgb(56, 190, 231);
}
</style>