<template>
    <div class="container">
        <div class="titulo">
            <h2>Página 1</h2>
            <br />
        </div>
        <div class="h-row">
            <div class="logo">
                <a
                    href="https://www.segundamano.mx"
                    title="Segundamano México: Anuncios clasificados gratis"
                    data-src="https://images.segundamano.mx/api/v1/smmx/images/static/logo_med.svg?rule=web_icon_1x"
                    lazy="loaded"
                    style="background-image: url('https://images.segundamano.mx/api/v1/smmx/images/static/logo_med.svg?rule=web_icon_1x');"
                ></a>
            </div>
            <br />
            <div class="header-container_general-info">
                <button type="button" class="publish-ad" @click="mostrarModal=true">
                    <a title="Ingresar">Ingresar</a>
                </button>
            </div>
        </div>

        <ModalIngresar v-model="mostrarModal" @getDatos="getDatos" />

        <div>
            <p>Resultado:</p>
            <br />
            <pre>
                {{ datosForm }}
            </pre>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                mostrarModal: false,
                datosForm: {},
            };
        },
        watch: {
            mostrarModal: function () {
                if (this.mostrarModal) {
                    this.datosForm = {};
                }
            },
        },
        methods: {
            getDatos(datosForm) {
                this.datosForm = datosForm;
                this.mostrarModal = false;
            },
        },
    };
</script>
