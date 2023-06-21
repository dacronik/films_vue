<template>
    <div class="card">
        <div class="card_image" v-for="foto in galeria" :key="foto.name">
            <img class="card-img-top" :src="foto.src" alt="image" @click="showDescription(foto.id)">
        </div>
    </div>
</template>

<script>
export default {
    name: 'espacio_galeria',
    props: {
        galeria:{
            type:Array,
            require: true
        }
    },
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
        showDescription(id){
            this.$emit('showDescription',id);
        }
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .card_image{
        width: 240px;
        margin: 0 auto;
        border: 2px solid grey;
        margin: 10px;
    }
</style>