<template>
  <div class="col-2 m-auto">
    <button
      @click="this.$parent.$parent.$parent.$parent.$emit('addItem', item)"
      class="btn btn-success"
    >
      +
    </button>
  </div>
  <div class="col-sm-4">
    <img class="img-fluid d-block" :src="item.image" :alt="item.name" />
  </div>
  <div class="col">
    <h3 class="text-primary">{{ item.name }}</h3>
    <p class="mb-0">{{ item.description }}</p>
    <div class="h5 float-right">
      <span class="label"></span><CurrPrice :amt="item.price"></CurrPrice>
    </div>
  </div>
</template>

<script>
import CurrPrice from '@/components/CurrPrice'
export default {
  props: ['item'],
  emits: ['addItem'],
  components: {
    CurrPrice
  }
}
</script>
