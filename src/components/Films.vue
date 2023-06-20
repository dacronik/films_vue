<template>
    <div class="container">
        <div class="films">
            <h2>Galería</h2>
            <div class="films_card">
                <div class="card">
                    <div class="card_image" v-for="film in films" :key="film.name">
                        <img class="card-img-top" :src="film.src" alt="image" @click="showDescription(film.id)">
                    </div>
                </div>
            </div>
        </div>
        <div class="description">
            <h2>Descripcíon</h2>
            <div class="description_body" v-if="selectFilm">
                <div class="card-items">
                    <div class="card">
                    <img class="card-img-top" :src="selectFilm.src" alt="Title">
                    <div class="card-body">
                        <h4 class="card-title">Autor: {{selectFilm.autor}}</h4>
                    </div>
                    <button class="btn btn-danger" @click="selectFilm=null">Cerrar descripción</button>
                </div>
                </div>
                <div class="card_description">
                    <p>{{selectFilm.description}}</p>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
export default {
    name: 'films-comp',
    // props: {},
    data: function(){
        return {
            films:[
                {
                    id:1, 
                    name:"film 1",
                    src:"https://picsum.photos/id/684/600/400", 
                    autor:"Zacarias Flores Del Campo",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
                {
                    id:2, 
                    name:"film 2", 
                    src:"https://picsum.photos/id/694/600/400", 
                    autor:"Soila Cerda",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
                {
                    id:3, 
                    name:"film 3", 
                    src:"https://picsum.photos/id/695/600/400", 
                    autor:"Elvis Tek",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
                {
                    id:4, 
                    name:"film 4", 
                    src:"https://picsum.photos/id/686/600/400", 
                    autor:"Elba Surero",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
                {
                    id:5, 
                    name:"film 5", 
                    src:"https://picsum.photos/id/687/600/400", 
                    autor:"Estevan Dido",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
                {
                    id:6, 
                    name:"film 6", 
                    src:"https://picsum.photos/id/688/600/400", 
                    autor:"Lola Mento",
                    description:`Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, optio distinctio, non expedita nostrum, assumenda quo quia doloribus sequi iure mollitia voluptatum voluptas omnis accusantium laboriosam quasi neque voluptatem voluptates!
                    Dolor delectus deleniti pariatur accusantium similique voluptates sequi beatae obcaecati, neque sint aperiam voluptas ea, doloremque praesentium at voluptatum repellat suscipit! Tempora pariatur molestiae, similique nam necessitatibus cumque aperiam? Dicta.
                    Doloremque reprehenderit ratione quaerat vitae ad quisquam quidem deleniti fugit eligendi maiores. Dolorum aliquam aliquid magnam fugiat tenetur, alias deleniti illo, repellendus, vel id sit laboriosam eos impedit provident! Suscipit.
                    Ipsa sed quidem accusantium velit rerum aliquid quo! Amet alias eum ratione nobis corrupti quidem commodi, laudantium aperiam ipsa illum perspiciatis deleniti rerum sapiente fugit sed rem beatae. Deleniti, omnis!`
                    },
            ],
            selectFilm: null,
        }
    },
    // computed: {},
    methods: {
        showDescription(id){
            const film = this.films.find((film) =>film.id==id);
            this.selectFilm=film
            
        },
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
    .container{
        width: 80%;
        border: 1px solid black;
        display: flex;
    }
    .films{
        flex-basis: 40%;
        max-height: 400px;
        overflow: auto;
    }
    .films_card{
        display: flex;
        justify-content: center;
    }
    .description{
        flex-basis: 60%;
    }
    .card_image{
        width: 240px;
        margin: 0 auto;
        border: 2px solid grey;
        margin: 10px;
    }
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