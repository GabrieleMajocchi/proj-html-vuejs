<script>
    export default {
        name: 'SingleFoodtype',
        props: {
            foodlist: Object,
        },
        data() {
            return {
                
            }
        },
        methods: {
            getCardImg(img){
                return new URL(`../../assets/img/${img}`, import.meta.url).href;
            }
        },
    }
</script>

<template>
    <div class="foodtypeCards d-flex m-auto">
        <div class="my-card d-flex flex-column align-items-center" v-for="foodtype in foodlist">
            <h1>{{foodtype.name}}</h1>
            <p>{{foodtype.type}}</p>
            <img :src="getCardImg(foodtype.img)" :alt="foodtype.type">
            <a href="#">Shop {{foodtype.section}}</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .foodtypeCards{
        width: 65%;
        .my-card{
            cursor: pointer;
            background-image: url('../../assets/img/foodbg.png');
            width: 100%;
            transition: all 0.3s;
            &:nth-child(2){
            margin: 0 14px;
            }
            &:hover{
                transition: all 0.3s;
                transform: scale(1.03);
                filter: brightness(1.3);
            }
            h1{
                font-family: 'Trocchi', Arial, Helvetica, sans-serif;
                font-weight: 400;
                font-size: 34px;
                color: $textColor;
                padding-top: 75px;
            }
            p{
                color: $textGreen;
                font-size: 20px;
            }
            img{
                width: 100%;
                padding: 40px 5rem 0;
            }
            a{
                font-size: 14px;
                margin-bottom: 50px;
                @include buttonOnlyGreen(0)
                
            }
        }
    }
</style>
