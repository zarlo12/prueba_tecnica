<template>
    <div>
        <span class="modal-login-title"> Iniciar sesión </span>
         
          <div>
              <form id="user-form" novalidate="novalidate">
                  <div>
                      <!---->
                      <div class="row">
                          
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
                                  <input type="password" autocomplete="on" id="login-password" name="login-password" placeholder="Tu contraseña" novalidate="novalidate" />
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
                          <div><button @click.prevent="handleLogin" class="btn primary login-submit-button">Entra</button></div>
                          <a rel="nofollow" class="recover-link"> ¿Olvidaste tu contraseña? </a>
                      </div>
                  </div>
              </form>
          </div>
          <div class="login-back-button" @click="$emit('crearCuenta')">
              <!---->
              <a> ¿No tienes cuenta? <u>Crea una nueva</u></a>
              <!---->
          </div>
    </div>
</template>

<script>
export default {
    name: "FormLogin",
    data() {
        return {
            
        }
    },
    methods: {
        handleLogin(){
            console.log("🚀 ~ file: index.vue ~ line 75 ~ handleLogin ~ handleLogin", true)

        }
    },
}
</script>