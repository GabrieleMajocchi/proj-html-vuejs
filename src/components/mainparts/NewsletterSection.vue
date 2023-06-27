<script>
    export default {
        name: 'NewsletterSection',
        data() {
            return {
                
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <div class="newsletter">
        <h1 class="fw-normal">Join our newsletter</h1>
        <p>Volutpat vel turpis nulla lorem sed semper. Aliquam sagittis sem libero viverra vehicula nullam ut nisl.</p>
        <input type="text" placeholder="Insert your email.."><a href="#">Subscribe</a>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .newsletter{
        background-image: url('../../assets/img/banner-7-2x-scaled.jpg');
        filter: brightness(0.96);
        width: 65%;
        margin: auto;
        background-size: 100%;
        height: 480px;
        padding: 100px 120px;
        h1{
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            font-size: 42px;
            margin-bottom: 30px;
        }
        p{
            font-size: 17px;
            line-height: 31px;
            margin-bottom: 60px;
            width: 55%;
        }
        input{
            border: none;
            background-color: $bgAlmond;
            padding: 18px 16px;
            border-radius: 30px;
            width: 400px;
            margin-right: 20px;
        }
        a{
            @include buttonSubscribe()
        }
    }
</style>
