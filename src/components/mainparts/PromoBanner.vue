<script>
    export default {
        name: 'PromoBanner',
        data() {
            return {
                
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <div class="promoBanner d-flex justify-content-center align-items-center">
        <img src="../../assets/img/food-transparent-5.png" alt="Food for animals" class="mt-3">
        <p class="m-0 mx-4">Get $25 OFF your first purchase of our homemade pet food!</p>
        <a href="#">Visit the shop</a>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;
    
    .promoBanner{
        background-color: $bgDarkGreen;
        background-image: url('../../assets/img/bg-transparent-3.png');
        font-size: 20px;
        img{
            height: 118px;
        }
        p, a{
            color: $textColor;
        }
    }
</style>
