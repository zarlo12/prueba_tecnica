<template>
    <div>
        <div  id="login-form" >
            <span  class="modal-login-title"> Crea una cuenta </span>
           
            <div >
                <form  id="user-form" novalidate="novalidate">
                    <div >
                        <!---->
                        <div  class="row">
                            <div  id="login-toogle-password" style="display: none;">
                                <div  class="form-input-toggle">
                                    <div >
                                        <label >
                                            <input  id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                            <div ><p >Ocultar</p></div>
                                            <p  class="tip error"></p>
                                        </label>
                                    </div>
                                </div>
                            </div>
                            <div   class="input-container">
                                <div  class="sw-InputText none">
                                    <input
                                        
                                        type="email"
                                        id="register-email"
                                        name="register-email"
                                        placeholder="Tu correo electrónico"
                                        pattern="^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$"
                                        required="required"
                                        displayicon="true"
                                    />
                                    <span  class="sw-InputText_Icon"></span>
                                </div>
                                <div  class="sw-InputText_Extra"><p  class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                        <div  class="row login-password-input">
                            <div  id="login-toogle-password" style="display: none;">
                                <div  class="form-input-toggle">
                                    <div >
                                        <label >
                                            <input  id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                            <div ><p >Mostrar</p></div>
                                            <p  class="tip error"></p>
                                        </label>
                                    </div>
                                </div>
                            </div>
                            <div   class="input-container">
                                <div  class="sw-InputText none">
                                    <input  type="password" id="register-password" name="register-password" placeholder="Tu contraseña" required="required" displayicon="true" minlength="5" />
                                    <span  class="sw-InputText_Icon"></span>
                                </div>
                                <div  class="sw-InputText_Extra"><p  class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                        <div  class="row">
                            <div  id="login-toogle-password" style="display: none;">
                                <div  class="form-input-toggle">
                                    <div >
                                        <label >
                                            <input  id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                            <div ><p >Mostrar</p></div>
                                            <p  class="tip error"></p>
                                        </label>
                                    </div>
                                </div>
                            </div>
                            <div   class="input-container">
                                <div  class="sw-InputText none">
                                    <input  type="password" id="register-confirm-password" name="register-confirm-password" placeholder="Repite tu contraseña" minlength="5" required="required" displayicon="true" />
                                    <span  class="sw-InputText_Icon"></span>
                                </div>
                                <div  class="sw-InputText_Extra"><p  class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                        <div  class="row">
                            <div  id="login-toogle-password" style="display: none;">
                                <div  class="form-input-toggle">
                                    <div >
                                        <label >
                                            <input  id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                            <div ><p >Ocultar</p></div>
                                            <p  class="tip error"></p>
                                        </label>
                                    </div>
                                </div>
                            </div>
                            <div   class="input-container">
                                <div  class="sw-InputText none">
                                    <input  type="tel" id="register-telephone" name="register-telephone" placeholder="Tu número de teléfono" displayicon="true" minlength="10" maxlength="10" hidden="hidden" />
                                    <span  class="sw-InputText_Icon"></span>
                                </div>
                                <div  class="sw-InputText_Extra"><p  class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                    </div>
                    <!---->
                    <div >
                        <!---->
                        <div  id="login-button-submit" class="row">
                            <div ><button  type="submit" class="btn primary login-submit-button">Crea una cuenta</button></div>
                            <!---->
                        </div>
                    </div>
                </form>
                <div  class="login-terms row" style="">
                    <div >
                        Al crear una cuenta, estoy de acuerdo con las
                        <a  href="https://ayudasegundamano.force.com/ayuda/s/news/t-rminos-y-condiciones-de-pago-20Y1J000000kCY6UAM" target="_blank" rel="noopener"> Condiciones de uso </a> y la
                        <a  href="https://ayudasegundamano.force.com/ayuda/s/news/aviso-de-privacidad-20Y1J000000kCLTUA2" target="_blank" rel="noopener"> Política de privacidad</a>.
                    </div>
                </div>
            </div>
            <div  class="login-back-button" @click="$emit('crearCuenta')">
                <a >¿Ya tienes cuenta? <u >Inicia sesión</u></a>
                <!----><!---->
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: "FormLogin",
}
</script>