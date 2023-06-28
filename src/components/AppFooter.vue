<script>
import TopFooter from './footerparts/TopFooter.vue'
import LowerFooter from './footerparts/LowerFooter.vue'
    export default {
        name: 'AppFooter',
        components: {
            TopFooter,
            LowerFooter,
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
    <footer>
        <TopFooter/>
        <LowerFooter/>
    </footer>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixins.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    footer{
        background-color: $bgDarkGreen;
        height: 750px;
    }
</style>
