<template>
    <div class="d-flex justify-content-center align-content-center m-2">
        <div v-for="(circle, index) in arrayFilter" :key="index">
            <div class="circle" :style="{'backgroundColor': circle.hex}" @click="$emit('changecolor', index)">
            </div>
        </div>
    </div>
    
</template>

<script>
    import  {store} from '../store.js'
    export default {
        name: 'Circlecomp',
        props: {
            arrayFilter: Array,
        },
        data(){
            return{
                store,
            }
        },
        mounted(){
            console.log(this.arrayFilter);
        },
        
    }
</script>

<style lang="scss" scoped>
    .circle{
        width: 50px;
        height: 50px;
        border-radius: 50%;
        background-color: red;
        margin: 10px;
        border: 1px solid black;
    }
</style>
