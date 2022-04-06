<template>
    <div class="header-container header-home">
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
            <div class="header-container_search"></div>
            <div class="header-container_general-info">
                <!---->
                <a href="https://www.segundamano.mx/tiendas" class="stores"> Tiendas </a>
                <div class="no-logged-items">
                    <div
                    
                        class="header-box-user-button header-icons-margin-half"
                        data-src="https://images.segundamano.mx/api/v1/smmx/images/static/icon-user.svg?rule=web_icon_1x"
                        lazy="loaded"
                        style="background-image: url('https://images.segundamano.mx/api/v1/smmx/images/static/icon-user.svg?rule=web_icon_1x');"
                    ></div>
                    <div>
                        <div @click="btnIngresa=true" tabindex="0" class="enter-login header-icons-margin header-valign-center">Ingresa</div>
                    </div>
                </div>
                <button type="button" class="publish-ad">
                    <a title="¡Publica ya!">¡Publica ya!</a>
                    <!---->
                </button>
            </div>
            <div class="header-box-menu-bg-layout"></div>
        </div>
    </div>

</template>

<script>
export default {
    data() {
        return {
            btnIngresa: false
        }
    },
}
</script>

<style scoped>
.header-container {
    display: flex;
    margin: auto;
    width: 100%;
    background: #fff;
    box-shadow: 0 0.1rem 0.3rem 0 rgb(29 29 29 / 10%), 0 0.1rem 0.2rem 0 rgb(29 29 29 / 20%);
}

.h-row {
    display: flex;
    margin: 1rem auto;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    position: relative;
    min-height: 5.5rem;
    width: 100%;
    max-width: 1024px;
    
}

.h-row .publish-ad {
    cursor: pointer;
    background: #ff5859;
    font-size: 1.4rem;
    border: 0;
    margin-left: 2.4rem;
    border-radius: 2px;
    box-shadow: 0 0.1rem 0.2rem 0 rgb(0 0 0 / 30%);
    font-weight: 700;
}
.h-row .publish-ad a {
    color: #fff;
    text-decoration: none;
    padding: 1rem;
    display: inline-block;
}

a {
    background-color: transparent;
    -webkit-text-decoration-skip: objects;
}



.h-row .stores {
    color: #666;
    text-decoration: none;
    border-right: 1px solid #eaeaea;
    padding: 1.3rem 1.6rem 1rem 0;
    margin-right: 1.6rem;
}



.logo {
    background-repeat: no-repeat;
    float: left;
    height: 3rem;
}

.logo a {
    background-size: cover;
    background-repeat: no-repeat;
    float: left;
    width: 21rem;
    height: 3rem;
}


.header-container_general-info {
    display: flex;
    justify-content: flex-end;
}

.header-box-menu-bg-layout {
    display: none;
    background-color: transparent;
    width: 100%;
    height: 100%;
    z-index: 999;
}

.header-icons-margin-half {
    margin-right: -0.2rem;
}

.header-box-user-button {
        background-size: 37.9px;
    width: 2.4rem;
    height: 2.4rem;
}



.header-icons-margin {
    margin: 0 0.8rem;
    padding: 0.5rem 0;
}

.enter-login {
    display: flex;
    color: #666;
    cursor: pointer;
}
.header-valign-center, .no-logged-items {
    align-items: center;
}



.header-valign-center, .no-logged-items {
    display: flex;
    align-items: center;
}




</style>