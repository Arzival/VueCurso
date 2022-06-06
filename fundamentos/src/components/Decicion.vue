<template>
    <div>
        <img :src="img" alt="bg" v-if="img" />
        <div class="bg-dark"></div>
        <div class="indecision-container">
            <input type="text" v-model="pregunta" placeholder="Hazme una pregunta" />
            <p>Recuerda terminar con un signo de intrregacion?</p>
            <div v-if="preguntaValida">
                <h2>{{ pregunta }}</h2>
                <h1> {{ respuesta }} </h1>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            pregunta: "",
            respuesta: "",
            img: null,
            preguntaValida: false
        };
    },
    watch: {
        pregunta(val) {
            this.preguntaValida = false
            if (!val.includes("?")) return
            this.preguntaValida = true;
            this.getRespuesta()
        },
    },
    methods: {
        async getRespuesta() {
            this.respuesta = 'Pensando...'

            const { answer, image } = await fetch('https://yesno.wtf/api').then(res => res.json())
            this.respuesta = answer == 'yes' ? 'Si' : 'No'
            this.img = image
        },
    },
}
</script>

<style scoped>
img,
.bg-dark {
    height: 100vh;
    left: 0px;
    max-height: 100%;
    max-width: 100%;
    position: fixed;
    top: 0px;
    width: 100vw;
}

.bg-dark {
    background-color: rgba(0, 0, 0, 0.4);
}

.indecision-container {
    position: relative;
    z-index: 99;
}

input {
    width: 250px;
    padding: 10px 15px;
    border-radius: 5px;
    border: none;
}

input:focus {
    outline: none;
}

p {
    color: white;
    font-size: 20px;
    margin-top: 0px;
}

h1,
h2 {
    color: white;
}

h2 {
    margin-top: 150px;
}
</style>