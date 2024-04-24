<template>
    <div class="d-flex justify-content-center align-content-center m-2">
        <div v-for="(circle, index) in store.colors" :key="index">
            <div class="circle" :style="{'backgroundColor': circle.hex}" @click="$emit('changecolor', index)">
            </div>
        </div>
    </div>
    
</template>

<script>
    import  {store} from '../store.js'
    export default {
        name: 'Circlecomp',
        data(){
            return{
                store
            }
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