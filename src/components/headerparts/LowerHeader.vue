<script>
    export default {
        name: 'LowerHeader',
        props: {
            navSections: Object,
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
    <nav class="d-flex m-auto">
        <div class="dropdown" v-for="element in navSections">
            <a class="nav-link fw-medium" :class="element.elements === undefined ? '' : 'dropdown-toggle'" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                {{element.name}}
            </a>
            <ul v-if="element.elements !== undefined" class="dropdown-menu p-0">
                <li v-for="item in element.elements"><a class="dropdown-item" href="#">{{item}}</a></li>
            </ul>
        </div>
    </nav>
    <div class="banner d-flex justify-content-around align-items-center">
        <p class="m-0"><i class="fa-regular fa-map"></i><span class="fw-semibold"> International</span> Shipping Services</p>
        <p class="m-0"><i class="fa-regular fa-clock"></i> See our <span class="fw-semibold">store hours and</span> services</p>
        <p class="m-0"><i class="fa-solid fa-check"></i> We price match to give you the <span class="fw-semibold">best deals</span></p>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/variables.scss' as *;

    nav{
        width: fit-content;
        color: grey;
    }
    .dropdown{
        padding: 16px 18px;
        ul{
            border: none;
            border-radius: 0;
            a{
                padding: 13px 16px;
                border-bottom: 1px solid $textGrey;
            }
            li:hover a{
                background-color: $bgGreen;
                color: $textColor;
                border-bottom: 1px solid $textGreen;
            }
        }
    }
    .dropdown:hover .dropdown-menu {
        display: block;
        margin-top: 0;
    }

    .dropdown:hover a{
        color: $textBlack;
    }
    .banner{
        height: 63px;
        width: 100%;
        background-color: $bgDarkGreen;
        background-image: url('../../assets/img/bg-transparent-3.png');
        color: $textColor;
        padding: 0 17rem;
        font-size: 15px;
    }
</style>
