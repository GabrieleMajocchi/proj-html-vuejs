<script>
export default {
    name: 'LowerFooter',
    data() {
        return {
            sections: ['Home', 'About', 'Blog', 'Contact', 'Shop']
        }
    },
    methods: {
        
    },
}
</script>

<template>
    <div class="lowerFooter text-center">
        <ul class="d-flex justify-content-center">
            <li v-for="section in sections"><a href="#">{{section}}</a></li>
        </ul>
        <div class="socials d-flex justify-content-center">
            <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
            <a href="#"><i class="fa-brands fa-twitter"></i></a>
            <a href="#"><i class="fa-brands fa-instagram"></i></a>
            <a href="#"><i class="fa-brands fa-youtube"></i></a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../../styles/partials/mixins.scss' as *;
@use '../../styles/partials/variables.scss' as *;

    .lowerFooter{
        li{
            list-style: none;
            margin: 60px 15px 30px 15px;
        }
        a{
            color: lightgray;
            text-decoration: none;
            &:hover{
                color: $textColor;
            }
        }
        .socials a{
            color: $textColor;
            margin: 0 12px;
            font-size: 20px;
            transition: all 0.3s ease-in-out;
            &:hover{
                transition: all 0.3s ease-in-out;
                color: $textGreen;
            }
        }
    }
</style>