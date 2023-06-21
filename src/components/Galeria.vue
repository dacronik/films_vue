<template>
    <div class="container">
        <div class="galeria">
            <h2>Galería</h2>
            <div class="galeria_card">
                <espacio-galeria :galeria="info" @showDescription="showDesc"/>
            </div>
        </div>
        <div class="description" > 
            <h2>Descripcíon</h2>
            <espacio-description  :description="selectImage" :show="show" @cerrarDesc="show=false"/>
        </div>
    </div>
</template>

<script>
import EspacioGaleria from "@/components/EspacioGaleria"
import EspacioDescription from "@/components/EspacioDescription"

export default {
    name: 'component-name',
    // props: {},
    data: function(){
        return {
            info:[
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
            selectImage: {},
            show: false
        }
    },
    // computed: {},
    methods: {
        showDesc(id){
            const image = this.info.find(foto => foto.id ==id)
            this.selectImage = image
            this.show = true
        }
    },
    // watch: {},
    components: {
        "espacio-galeria":EspacioGaleria,
        "espacio-description":EspacioDescription
    },
    // mixins: [],
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
    .galeria{
        flex-basis: 40%;
        max-height: 400px;
        overflow: auto;
    }
    .galeria_card{
        display: flex;
        justify-content: center;
    }
    .description{
        flex-basis: 60%;
    }
</style>