<template>
  <div class="hello">
    <button class="btn btn-success btn-lg" @click="showModal=true">Modal</button>
    <Modal v-model="showModal"></Modal>
  </div>
</template>

<script>
import Modal from '@/components/Modal';

export default {
  name: 'HelloWorld',
  components: {
    Modal
  },
  data () {
    return {
      showModal: false
    }
  }
}
</script>