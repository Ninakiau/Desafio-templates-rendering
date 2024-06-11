<script>
export default {
    name: 'Formulario',
    data() {
        return {
            colorFondo: '',
            ux: true,
            colorLetra: '',
            mostrar: false,
            texto: '',
            borde: 0,
            tipografia: '',
            opaco: true,
            tamanoLetra: '',

        }
    },

}
</script>

<template>
    <main>
        <div class="form">
            <label for="text">Color de fondo</label>
            <input type="text" placeholder="darkgreen, red, yellow" v-model="colorFondo">
            <label for="text">Color de texto</label>
            <input type="text" placeholder="white, black, blue" v-model="colorLetra">
            <div>
                <label for="text">Mostrar texto</label>
                <input type="checkbox" v-model="mostrar">
            </div>
            <label>Borde</label>
            <input type="range" v-model="borde" min="0" max="50">
            <label for="text">Contenido textual</label>
            <textarea v-model="texto"></textarea>
            <label for="select">Tipografia</label>
            <select name="select" id="select" v-model="tipografia">
                <option value="Cursive">Cursive</option>
                <option value="Arial">Arial</option>
                <option value="Courier New">Courier New</option>
                <option value="Georgia">Georgia</option>
                <option value="Times New Roman">Times New Roman</option>
                <option value="Trebuchet MS">Trebuchet MS</option>
                <option value="Verdana">Verdana</option>
                <option value="Comic Sans MS">Comic Sans MS</option>
            </select>
            <div><label for="checkbox">Opaco</label>
                <input type="checkbox" v-model="opaco">
            </div>


            <label for="checkbox">Tamaño de letra</label>
            <div class="form-radio">
                <label for="small">Pequeño</label>
                <input type="radio" name="size" value="pequeno" v-model="tamanoLetra">
                <label for="medium">Mediano</label>
                <input type="radio"  name="size" value="mediano" v-model="tamanoLetra">
                <label for="large">Grande</label>
                <input type="radio" name="size" value="grande" v-model="tamanoLetra">
            </div>


        </div>
        <div>
            <div v-show="mostrar">
                <h1 :class="{ ux , pequeno: tamanoLetra === 'pequeno', mediano: tamanoLetra === 'mediano', grande: tamanoLetra === 'grande'}" :style="{
                    backgroundColor: colorFondo,
                    color: colorLetra,
                    borderRadius: borde + 'px',
                    fontFamily: tipografia,
                    opacity: opaco ? 1 : 0.5,
                }">{{ texto }}</h1>
            </div>
        </div>
    </main>

</template>

<style>
.form {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
    margin: 3rem;
    background-color: rgb(34, 104, 75);
    color: white;
    padding: 2rem;
}

main {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10rem;
}

.ux {
    padding: 5rem;
}

.pequeno {
    font-size: 1rem;
}

.mediano {
    font-size: 2rem;
}

.grande {
    font-size: 3rem;
}
</style>