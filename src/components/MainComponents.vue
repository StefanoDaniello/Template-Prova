<template>
    <main class="container ">
        <Circlecomp @changecolor="changecolor"/>
        <div class="square" ref="square"></div>
    </main>
</template>

<script>
import Circlecomp from './Circlecomp.vue';
import {store} from '../store.js';
    export default {
        name: 'MainComponents',
        components: {
            Circlecomp,
        },
        data(){
            return{
                store
            }
        },
        methods:{
            changecolor(index){
                this.$refs.square.style.backgroundColor = this.store.colors[index].hex;
            }
        },
    }
</script>

<style lang="scss" scoped>
    .square{
        width: 550px;
        height: 350px;
        border: 1px solid black;
        margin: 20px auto;
    }
</style>