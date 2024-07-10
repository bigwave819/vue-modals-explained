<template>
    <div>
        <h2>{{ title }}</h2>
        <p>Loading ...</p>
        <div v-if="showModal">
            <ModalOne theme="sales" @close="ToggleModal">
                <h1>Sign up for the Giveaway!</h1>
                <p>give your waving swag for the half price</p>
            </ModalOne>
        </div>
        <button @click="ToggleModal">
            show Modal
        </button>
    </div>
</template>
<script>
import ModalOne from './components/ModalOne.vue'
export default {
    components: { ModalOne },
    data(){
        return{
            title: 'Hello world :-)',
            showModal: false
        }
    },
    methods: {
        ToggleModal () {
            this.showModal = !this.showModal
        }
    }
}
</script>
<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>