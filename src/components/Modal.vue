<template>
  <div :value="value" v-show="visible" @keyup.esc="visible=false">
      <div class="modal-mask">
        <div class="modal-wrapper" @click="visible=false">
          <div class="modal-container col-md-6" @click.stop>
            <div class="modal-header">
              <slot name="modal-header"></slot>

              <a class="btn-close" @click="visible = false">
              	<i class="fa fa-times-circle"></i>
              </a>
            </div>
            
            <slot name="modal-body"></slot>

            <div class="modal-footer j-forms">
              <div name="footer">
                <button class="btn btn-primary">
                  Submit
                </button>
                <button class="btn btn-primary" @click="visible = false">
                  Cancel
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'Modal',
  data () {
    return {
      visible: false
    }
  },
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  watch:{
    value(val){
      this.visible = val
    },
    visible(val){
      this.$emit('input', val)
    }
  },
  mounted(){
    if(this.value){
      this.visible = true
    }
  }
}
</script>

 <style>
 @import '../assets/css/Modal.css'
</style>