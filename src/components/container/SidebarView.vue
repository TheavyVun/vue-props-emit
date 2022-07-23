<template>
    <div class="sidebar">
        <form-view />
    </div>
</template>

<script>
import FormView from './FormView.vue'
export default {
    components: {
        'form-view': FormView,
    },
    props: {
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .sidebar {
        width: 40%;
        padding: 20px;
        border-right: 1px dotted black;
    }
</style>