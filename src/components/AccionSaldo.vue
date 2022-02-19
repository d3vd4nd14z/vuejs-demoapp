<template>    
    <v-btn @click="operacion" :disabled="desactivar" color="primary" dark>
        {{ texto }}
    </v-btn>      
</template>

<script>
export default {
    props: {
        texto: String,
        desactivar: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        operacion(){
            this.$emit('accion')
        }
    }
}
</script>

<style>

</style>