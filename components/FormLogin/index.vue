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
                                <input
                                    type="email"
                                    v-model="formLogin.correo"
                                    id="login-email"
                                    name="login-email"
                                    placeholder="Tu correo electrónico"
                                    pattern="^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$"
                                    displayicon="true"
                                    required="required"
                                />
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
                                        <input v-model="mostrarPassword" id="ai-toggle-password" type="checkbox" name="toggle-password" />
                                        <div><p>{{ mostrarPassword ? 'Ocultar' : 'Mostrar' }}</p></div>
                                        <p class="tip error"></p>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <div class="input-container">
                            <div class="sw-InputText none">
                                <input :type="tipoInputPassword" v-model="formLogin.password" autocomplete="on" id="login-password" name="login-password" placeholder="Tu contraseña" novalidate="novalidate" />
                                <!---->
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
                formLogin: {
                    correo: "",
                    password: "",
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
            async handleLogin() {
                try {
                    await this.validarCampos();

                    //enviar datos al componente padre
                    this.$emit("getDatos", this.formLogin);
                } catch (error) {
                    this.mensajeError = error;
                }
            },

            validarCampos() {
                return new Promise((resolve, reject) => {
                    const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                    if (!re.test(String(this.formLogin.correo).toLowerCase())) {
                        reject("El correo no es válido");
                    }

                    const reExPassword = /^(?=.*[A-Z])(?=.*\d).*$/;
                    if (!reExPassword.test(String(this.formLogin.password))) {
                        reject("Las contraseñas deben tener al menos una letra mayúscula y un número.");
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
