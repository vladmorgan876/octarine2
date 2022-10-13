<template>
    <div>
        <canvas id="canvas"></canvas>
    </div>
</template>

<script>
import {mapActions} from "vuex";
import {earth3d} from '../MyClass/Fons3d';
export default {
    name: "ThreeComponent2",
    data(){
        return{

        }
    },
    methods: {
        flagscreen: function () {
            this.$store.dispatch('ActionFlagScreen', 'shown');
        },
        ...mapActions([
            'GET_PRODUCTS_FROM_API'
        ]),
    },
    mounted() {
        this.GET_PRODUCTS_FROM_API();
        earth3d();
        setTimeout(this.flagscreen, 15000);
    }
}
</script>

<style scoped>
#canvas{
    background-image:url("/storage/newimage/cosmos.jpg");
    width: 100%;
    height: 100%;
}
</style>
