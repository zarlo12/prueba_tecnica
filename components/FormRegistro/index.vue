<template>
    <div>
        <div id="login-form">
            <span class="modal-login-title"> Crea una cuenta </span>

            <div>
                <form id="user-form" novalidate="novalidate">
                    <div>
                        <!---->
                        <div class="row">
                            <div class="input-container">
                                <div class="sw-InputText none">
                                    <input
                                        v-model="formRegistro.correo"
                                        type="email"
                                        id="register-email"
                                        name="register-email"
                                        placeholder="Tu correo electrónico"
                                        pattern="^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$"
                                        required="required"
                                        displayicon="true"
                                    />
                                    <span class="sw-InputText_Icon"></span>
                                </div>
                                <div class="sw-InputText_Extra"><p class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                        <div class="row login-password-input">
                            <div class="input-container">
                                <div class="sw-InputText none">
                                    <input v-model="formRegistro.password" type="password" id="register-password" name="register-password" placeholder="Tu contraseña" required="required" displayicon="true" minlength="5" />
                                    <span class="sw-InputText_Icon"></span>
                                </div>
                                <div class="sw-InputText_Extra"><p class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="input-container">
                                <div class="sw-InputText none">
                                    <input
                                        v-model="formRegistro.password_confirm"
                                        type="password"
                                        id="register-confirm-password"
                                        name="register-confirm-password"
                                        placeholder="Repite tu contraseña"
                                        minlength="5"
                                        required="required"
                                        displayicon="true"
                                    />
                                    <span class="sw-InputText_Icon"></span>
                                </div>
                                <div class="sw-InputText_Extra"><p class="sw-InputText_Message"></p></div>
                            </div>
                        </div>
                    </div>
                    <!---->

                    <div class="alert" v-if="mensajeError">
                        <span class="closebtn" @click="mensajeError=''">&times;</span>
                        {{ mensajeError }}
                    </div>

                    <div>
                        <!---->
                        <div id="login-button-submit" class="row">
                            <div><button @click.prevent="handleRegistro" class="btn primary login-submit-button">Crea una cuenta</button></div>
                            <!---->
                        </div>
                    </div>
                </form>
                <div class="login-terms row" style="">
                    <div>
                        Al crear una cuenta, estoy de acuerdo con las
                        <a href="https://ayudasegundamano.force.com/ayuda/s/news/t-rminos-y-condiciones-de-pago-20Y1J000000kCY6UAM" target="_blank" rel="noopener"> Condiciones de uso </a> y la
                        <a href="https://ayudasegundamano.force.com/ayuda/s/news/aviso-de-privacidad-20Y1J000000kCLTUA2" target="_blank" rel="noopener"> Política de privacidad</a>.
                    </div>
                </div>
            </div>
            <div class="login-back-button" @click="$emit('crearCuenta')">
                <a>¿Ya tienes cuenta? <u>Inicia sesión</u></a>
                <!----><!---->
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "FormRegistro",
        data() {
            return {
                formRegistro: {
                    correo: "",
                    password: "",
                    password_confirm: "",
                },
                mensajeError: "",
                mostrarPassword: false,
            };
        },
        computed: {
            tipoInputPassword() {
                return this.mostrarPassword ? "text" : "password";
            },
        },
        methods: {
            async handleRegistro() {
                try {
                    await this.validarCampos();

                    //enviar datos al componente padre
                    this.$emit("getDatos", this.formRegistro);
                } catch (error) {
                    this.mensajeError = error;
                }
            },

            validarCampos() {
                return new Promise((resolve, reject) => {
                    const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                    if (!re.test(String(this.formRegistro.correo).toLowerCase())) {
                        reject("El correo no es válido");
                    }

                    const reExPassword = /^(?=.*[A-Z])(?=.*\d).*$/;
                    if (!reExPassword.test(String(this.formRegistro.password))) {
                        reject("Las contraseña debe tener al menos una letra mayúscula y un número.");
                    }

                    if (this.formRegistro.password_confirm != this.formRegistro.password) {
                        reject("Las contraseñas no coinciden, verificarlas");
                    }

                    resolve(true);
                });
            },
        },
    };
</script>

<style scoped>
    .alert {
        padding: 20px;
        background-color: #f4433652;
        color: #333333;
    }

    .closebtn {
        margin-left: 15px;
        color: rgb(185, 11, 11);
        font-weight: bold;
        float: right;
        font-size: 22px;
        line-height: 20px;
        cursor: pointer;
        transition: 0.3s;
    }

    .closebtn:hover {
        color: black;
    }
</style>
