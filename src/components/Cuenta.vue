<template>
    <h3>Saldo: {{saldo}}</h3>
    <h3>Cuenta: {{cuenta}}</h3>
    <h3>Estado: {{estado? 'Cuenta Activa' : 'Cuenta Desactivada'}}</h3>
    <hr>
    <h4>Servicios Disponibles</h4>
    <div v-for="(item, index) in servicios" :key="index">
        {{index +1}} - {{ item }}
    </div>
    <BotonSaldo texto="Aumentar Saldo" @signal="agregarSaldo"></BotonSaldo>
    <BotonSaldo texto="Disminuir Saldo" @signal="disminuirSaldo" :desactivar="desactivar"></BotonSaldo>
    
</template>

<script>
import BotonSaldo from './BotonSaldo'
export default {
    components: {
        BotonSaldo,
    },
    data() {
        return {
            saldo: 1000,
            cuenta:'Visa',
            estado: true,
            servicios:['pagos','giros','transferencias'],
            desactivar:false
        }
    },
    methods: {
        agregarSaldo() {
            this.saldo = this.saldo + 100
        },
        disminuirSaldo() {
            if (this.saldo === 0) {
                this.desactivar = true
            } else {
                this.saldo = this.saldo - 100
            }
               
           
             
        }
    },
}
</script>

<style>
   li{
       list-style: none;
       text-transform: uppercase;
       margin: 5px;
   }
</style>