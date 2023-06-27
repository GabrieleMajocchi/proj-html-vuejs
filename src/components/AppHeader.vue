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
                navSections: [{name: 'Home', elements: ['Home - Alternate']},
                                {name: 'Shop', elements: ['Shop no sidebar', 'Shop single sidebar', 'Shop dual sidebar', 'Simple product', 'variable product']},
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
    @use '../styles/partials/mixins.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    hr{
        color: grey;
    }
</style>
