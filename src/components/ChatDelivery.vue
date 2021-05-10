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
export default {
  name: 'ChatDelivery',
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