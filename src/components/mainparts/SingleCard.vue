<script>
    export default {
        name: 'SingleCard',
        props: {
            card: Object,
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
    <div class="singleCardBrowse d-flex" v-if="card.name === 'browse'">
        <div class="my-card" v-for="n in (card.section.length)">
            <img :src='getCardImg(card.img[n-1])' alt="Product Image">
            <p class="m-0">{{card.section[n-1]}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .singleCardBrowse{
        text-align: center;
        font-size: 25px;
        width: 65%;
        margin: auto;
        img{
            width: 100%;
        }
        .my-card{
            margin: 48px 12px;
        }
        .my-card:hover p{
            color: $textGreen;
        }
    }
</style>
