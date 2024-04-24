<template>
    <main class="container ">
        <FilterComp @filter="filter"/>
        <Circlecomp @changecolor="changecolor" :arrayFilter="arrayFilter"/>
        <div class="square text-center" ref="square">
            <h1>{{label}}</h1>
            <h3>{{hex}}</h3>
            <h3>{{palette_name}}</h3>
        </div>
    </main>
</template>

<script>
import Circlecomp from './Circlecomp.vue';
import FilterComp from './FilterComp.vue';
import {store} from '../store.js';
    export default {
        name: 'MainComponents',
        components: {
            Circlecomp,
            FilterComp
        },
        data(){
            return{
                store,
                arrayFilter: [],
                label: '',
                hex: '',
                palette_name: ''
            }
        },
        methods:{
            changecolor(index){
                this.$refs.square.style.backgroundColor = this.arrayFilter[index].hex;
                this.label =this.arrayFilter[index].label
                this.hex =this.arrayFilter[index].hex
                this.palette_name =this.arrayFilter[index].palette_name

            },
            filter(event){
                this.arrayFilter = [];
                let array = [];
                if(event === ''){
                    array = this.store.colors;

                }else{
                    array = this.store.colors.filter((color) => color.palette_name === event);
                }
                this.arrayFilter.push(...array);
                console.log(this.arrayFilter);
            }
        },
        mounted(){
            this.arrayFilter = this.store.colors
            console.log(this.arrayFilter);
        }
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