<template>

  <div class="delivery-wrapper">
    <div>
      <h5>{{ delivery1.version }}</h5>
      <p class="delivery-name">{{ delivery1.name }}</p>
      <p>{{ delivery1.type }} {{ delivery1.size }} - {{ delivery1.date }}</p>
    </div>
    <div>
      <a :href="delivery1.url"><i class="fas fa-cloud-download-alt"></i></a>
    </div>
  </div>

    <div class="delivery-wrapper">
    <div>
      <h5>{{ delivery2.version }}</h5>
      <p class="delivery-name">{{ delivery2.name }}</p>
      <p>{{ delivery2.type }} {{ delivery2.size }} - {{ delivery2.date }}</p>
    </div>
    <div>
      <a :href="delivery2.url"><i class="fas fa-cloud-download-alt"></i></a>
    </div>
  </div>

</template>

<script>
import { Delivery } from '@/models/delivery.js'
import { ref } from 'vue'

export default {
  name: 'Delivery',
  setup() {
    let delivery1 = ref(new Delivery('VERSIÓN 1', 'Título del archivo a subir 1.pdf', 'Documento/PDF', '(3.8 MB)', '28 dic 2018/14:45', 'url'))

    let delivery2 = ref(new Delivery('VERSIÓN 2', 'Título del archivo a subir 2.pdf', 'Documento/PDF', '(4.8 MB)', '30 dic 2018/8:22', 'url'))

    
    return { delivery1, delivery2 }
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