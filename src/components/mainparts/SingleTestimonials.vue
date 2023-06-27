<script>
    export default {
        name: 'SingleTestimonials',
        props: {
            testimonials: Object,
        },
        data() {
            return {
                
            }
        },
        methods: {
            getUserImg(img){
                return new URL(`../../assets/img/${img}`, import.meta.url).href;
            }
        },
    }
</script>

<template>
    <div class="reviews d-flex m-auto">
        <div class="review" v-for="review in testimonials">
            <img :src="getUserImg(review.img)" alt="Image of the user">
            <p>{{review.review}}</p>
            <p>{{review.name}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .reviews{
        width: 65%;
        text-align: center;
        .review{
            margin: 4rem 3rem;
            img{
                border-radius: 50%;
                width: 100px;
                margin-bottom: 1.5rem;
            }
            p{
                color: $textColor;
                font-size: 17px;
                line-height: 31px;
                &:nth-child(3){
                    color: rgba(255, 255, 255, 0.56)
                }
            }
        }
    }
</style>
