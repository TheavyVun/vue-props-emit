<template>
    <div class="container">
        <side-bar />
        <main-view />
    </div>
</template>

<script>
import Sidebar from './SidebarView.vue'
import MainView from './MainView.vue'
export default {
    components: {
        'side-bar': Sidebar,
        'main-view': MainView,
    },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .container {
        display: flex;
        box-sizing: border-box;
    }
</style>