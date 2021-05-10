<template>

  <div class="delivery-wrapper">
    <div>
      <h5>
        <slot name="version"></slot>
      </h5>
      <p class="delivery-name">
        <slot name="name"></slot>
      </p>
      <p>
        <slot name="info"></slot>
      </p>
    </div>
    <div>
      <slot name="download"></slot>
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

@media only screen and (max-width: 590px) {
  .delivery-wrapper {
    flex-direction: column;
    font-size: 0.9rem;
  }

  .fa-cloud-download-alt {
    margin-bottom: 1rem;
  }
  
}
</style>