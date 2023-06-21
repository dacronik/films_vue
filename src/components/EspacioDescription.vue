<template>
    <div class="description_body" v-if="show">
        <div class="card-items">
            <div class="card">
            <img class="card-img-top" :src="description.src" alt="Title" srcset="">
            <div class="card-body">
                <h4 class="card-title">Autor: {{description.autor}}</h4>
            </div>
                <button class="btn btn-danger" @click="closeDescription">Cerrar descripción</button>
            </div>
        </div>
        <div class="card_description">
            <p>{{description.description}}</p>
        </div>
    </div>
    
</template>

<script>
export default {
    name: 'espacio-descripcion',
    props: {
        description:{
            type: Object,
            required: true,
        },
        show:{
            type:Boolean,
            required: true
        } 
        
    },
    data: function(){
        return {
        }
    },
    // computed: {},
    methods: {
        closeDescription(){
            this.$emit('cerrarDesc')
        }
    },
    // watch: {},
    //components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .description_body{
        display: flex;
    }
    .card-items{
        width: 40%;
    }
    .card_description{
        border: 1px solid grey;
        width: 60%;
        max-height: 400px;
        overflow: auto;
    }
    button{
        margin: 20px 30px 20px 30px;
    }
</style>