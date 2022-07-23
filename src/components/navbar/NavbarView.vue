<template>
    <nav>
        <ul>
            <nav-list list="Home" />
            <nav-list list="About" />
            <nav-list list="Serves" />
            <nav-list list="Contact Us" />
        </ul>
    </nav>
</template>

<script>
import NavList from './ListView.vue'
export default {
    components: {
        'nav-list': NavList,
    },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    nav {
        background-image: linear-gradient(to top, #30cfd0 0%, #330867 100%);        
    }
    ul {
        display: flex;
        margin: 0;
    }

</style>