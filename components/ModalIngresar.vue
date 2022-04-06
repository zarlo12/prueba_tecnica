<template>
   
        <div class="details-modal " v-if="selectVal ">
      <div class="details-modal-close" @click="cerrarModal()">
        X
      </div>
     
      <div class="details-modal-content">
        <div id="login-form" data-v-26e2201c="">
          <span class="modal-login-title"> Iniciar sesión </span>
          <div class="modal-facebook-login">
              <div>
                  <div data-width="380" data-max-rows="1" data-size="large" data-button-type="login_with" data-use-continue-as="true" data-scope="email" onlogin="onLoginCallback" class="fb-login-button"></div>
                  <!----><!---->
              </div>
          </div>
          <div>
              <form id="user-form" novalidate="novalidate">
                  <div>
                      <!---->
                      <div class="row">
                          <div id="login-toogle-password" style="display: none;">
                              <div class="form-input-toggle">
                                  <div>
                                      <label>
                                          <input id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                          <div><p>Ocultar</p></div>
                                          <p class="tip error"></p>
                                      </label>
                                  </div>
                              </div>
                          </div>
                          <div class="input-container">
                              <div class="sw-InputText none">
                                  <input type="email" id="login-email" name="login-email" placeholder="Tu correo electrónico" pattern="^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$" displayicon="true" required="required" />
                                  <span class="sw-InputText_Icon"></span>
                              </div>
                              <div class="sw-InputText_Extra"><p class="sw-InputText_Message"></p></div>
                          </div>
                      </div>
                      <div class="row login-password-input">
                          <div id="login-toogle-password">
                              <div class="form-input-toggle">
                                  <div>
                                      <label>
                                          <input id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                          <div><p>Mostrar</p></div>
                                          <p class="tip error"></p>
                                      </label>
                                  </div>
                              </div>
                          </div>
                          <div class="input-container">
                              <div class="sw-InputText none">
                                  <input type="password" id="login-password" name="login-password" placeholder="Tu contraseña" novalidate="novalidate" />
                                  <!---->
                              </div>
                              <div class="sw-InputText_Extra"><p class="sw-InputText_Message"></p></div>
                          </div>
                      </div>
                  </div>
                  <!---->
                  <div>
                      <!---->
                      <div id="login-button-submit" class="row">
                          <div><button type="submit" class="btn primary login-submit-button">Entra</button></div>
                          <a rel="nofollow" class="recover-link"> ¿Olvidaste tu contraseña? </a>
                      </div>
                  </div>
              </form>
              <div class="login-terms row" style="display: none;">
                  <div>
                      Al crear una cuenta, estoy de acuerdo con las
                      <a href="https://ayudasegundamano.force.com/ayuda/s/news/t-rminos-y-condiciones-de-pago-20Y1J000000kCY6UAM" target="_blank" rel="noopener"> Condiciones de uso </a> y la
                      <a href="https://ayudasegundamano.force.com/ayuda/s/news/aviso-de-privacidad-20Y1J000000kCLTUA2" target="_blank" rel="noopener"> Política de privacidad</a>.
                  </div>
              </div>
          </div>
          <div class="login-back-button">
              <!---->
              <a> ¿No tienes cuenta? <u>Crea una nueva</u></a>
              <!---->
          </div>
      </div>

      </div>
    </div>
   
</template>

<script>
export default {
  name: 'ModalIngresar',
  props: {
    value: ''

  },
  data() {
    return {
      
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