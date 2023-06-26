<script>
import FirstSection from './mainparts/FirstSection.vue';
import PromoBanner from './mainparts/PromoBanner.vue';
    export default {
        name: 'AppMain',
        components: {
            FirstSection,
            PromoBanner,
        },
        data() {
            return {
                
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
        <!-- ---Food type card--- -->
        <!-- ---New arrivals weekly--- -->
        <!-- ---Items everyone loves--- -->
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

</style>
