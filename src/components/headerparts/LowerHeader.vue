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
            <a class="nav-link fw-semibold" :class="element.elements === undefined ? '' : 'dropdown-toggle'" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                {{element.name}}
            </a>
            <ul v-if="element.elements !== undefined" class="dropdown-menu p-0">
                <li v-for="item in element.elements"><a class="dropdown-item" href="#">{{item}}</a></li>
            </ul>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixing.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    nav{
        width: fit-content;
        color: grey;
    }
    .dropdown{
        padding: 16px 18px;
        ul{
            border: none;
            a{
                padding: 13px 16px;
                border-bottom: 1px solid $textGrey;
            }
            li:hover a{
                background-color: $bgGreen;
                color: $textColor;
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
</style>
