<template>
   
        <div class="details-modal " v-if="selectVal ">
      <div class="details-modal-close" @click="cerrarModal()">
        X
      </div>
     
      <div class="details-modal-content">
        <div id="login-form">

        <FormLogin @crearCuenta="crearCuenta=true" v-if="!crearCuenta" /> 
        <FormRegistro @crearCuenta="crearCuenta=false" v-else /> 

      </div>

      </div>
    </div>
   
</template>

<script>
import FormLogin from '@/components/FormLogin'
import FormRegistro from '@/components/FormRegistro'
export default {
  name: 'ModalIngresar',
  computed: {
      FormLogin,
      FormRegistro
  },
  props: {
    value: ''

  },
  data() {
    return {
        crearCuenta: false,
    }
  },
  created() {
    
  },
  computed: {
        selectVal: {
            get() {
                return this.value
            },
            set(val) {
                this.$emit('input', val)
            }
        },

    },
    methods: {
      cerrarModal(){
        console.log('Cerrar modal');
        this.selectVal=false
      }
    },
}
</script>
