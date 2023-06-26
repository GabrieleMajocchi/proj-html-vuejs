<script>
import FirstSection from './mainparts/FirstSection.vue';
import PromoBanner from './mainparts/PromoBanner.vue';
import SingleCard from './mainparts/SingleCard.vue';
    export default {
        name: 'AppMain',
        components: {
            FirstSection,
            PromoBanner,
            SingleCard,
        },
        data() {
            return {
                arrayCard: [{name: 'browse', section: ['Bed (1)', 'Food (6)', 'Toys (6)', 'Transport (7)'], img: ['product-9.jpg', 'product-3.jpg', 'product-2.jpg', 'product-4.jpg']}, 
                            {name: 'bestsellers', section: ['Transport cage', 'Dog leash', 'Animal transport cage', 'Colorful cat leash'], price: ['$25.00', '$25.00', '<span class="text-decoration-line-through">$35.00</span> $25.00', '$12.00']},
                            {name: 'articles', section: ['How to ‘loose leash walk’ your dog', 'Stop cats from scratching furniture', 'Where to buy the best pet food', 'Proper care for your pet toys'], date: ['April 21st, 2020', 'April 19st, 2020', 'April 18st, 2020', 'April 17st, 2020']}
                    ],
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <main>
        <!-- ---First section, slogan--- -->
        <FirstSection/>
        <!-- ---Promo banner--- -->
        <PromoBanner/>
        <!-- ---Browse by category--- -->
        <div class="browse d-flex flex-column">
            <h1 class="m-auto">Browse by category</h1>
            <p class="m-auto text-center">Augue purus et, tincidunt condimentum mauris. At nibh rutrum mi in. Nisi, vitae interdum eleifend dui, consequat nulla rhoncus dictum. Viverra.</p>
            <SingleCard :card="arrayCard[0]"/>
        </div>
        <!-- ---Food type card--- -->
        <!-- ---New arrivals weekly--- -->
        <!-- ---All-time best sellers--- -->
        <!-- ---Users testimonials--- -->
        <!-- ---Newsletter--- -->
        <!-- ---Tips and tricks--- -->
        <!-- ---Big pic and infos--- -->
        <!-- ---New products arrival--- -->
    </main>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixins.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    .browse{
        margin-top: 100px;
        p{
            width: 30%;
        }
    }
</style>
