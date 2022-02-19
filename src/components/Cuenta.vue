<template>  
    <v-container>
        <v-row class="text-center">
            <v-col cols="4">
            <h4>Tipo de Cuenta: {{ cuenta }}</h4>
            </v-col>
            <v-col cols="4">
            <h4>Saldo: {{ saldo }}</h4>
            </v-col>
            <v-col cols="4">
            <h4>Estado: {{ estado ? 'Activa' : 'Desactivada'  }}</h4>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="12">
                <div v-for="(serv, index) in servicios" :key="index">
                    {{ index+1 }} - {{ serv }}
                </div>
            </v-col>
        </v-row>
        <AccionSaldo texto="Aumentar Saldo" @accion="aumentar"/>&nbsp;&nbsp;&nbsp;
        <AccionSaldo texto="Disminuir Saldo" @accion="disminuir" :desactivar="desactivar"/>
    </v-container>    
</template>

<script>

import AccionSaldo from './AccionSaldo.vue'

export default {
    components: {
        AccionSaldo
    },
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            servicios: ['Giros', 'Abonos', 'Transferencias'],
            desactivar: false            
        }
    },
    methods: {
        aumentar(){
            this.saldo = this.saldo + 100; 
            this.estado = true;
            this.desactivar = false;                           
        },
        disminuir(){
            if (this.estado == true){
                if (this.saldo >= 100){
                    this.saldo = this.saldo - 100;
                    if (this.saldo == 0){
                        this.estado = false;
                        this.desactivar = true;
                    }
                }
            }                        
        }
    }
}
</script>

<style>

</style>