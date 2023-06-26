<script>
import TopHeader from './headerparts/TopHeader.vue'
import LowerHeader from './headerparts/LowerHeader.vue'
    export default {
        name: 'AppHeader',
        components: {
            TopHeader,
            LowerHeader,
        },
        data() {
            return {
                navSections: [{name: 'Home', element1: 'Home - Alternate'},
                                {name: 'Shop', element1: 'Shop no sidebar', element2: 'Shop single sidebar', element3: 'Shop dual sidebar', element4: 'Simple product', element5: 'variable product'},
                                {name: 'About'},
                                {name: 'Blog'},
                                {name: 'Contact'},
                                {name: 'Shop by brand'}
                    ],
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <header>
        <!-- ---Top header with Logo, search and user icon--- -->
        <TopHeader/>
        <hr class="m-0">
        <!-- ---Lower header with navbar--- -->
        <LowerHeader :navSections="navSections"/>
    </header>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    hr{
        color: grey;
    }
</style>
