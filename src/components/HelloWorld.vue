<template>
  <div class="hello">
    <button class="btn btn-success btn-lg" @click="showModal=true">Modal</button>
    <Modal v-model="showModal">
      <div slot="modal-header" name="header">
        Reusable Modal Header
      </div>
      <h1 slot="modal-body">Modal Body</h1>
    </Modal>
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