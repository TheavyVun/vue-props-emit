<template>
    <li>{{list}}</li>
</template>

<script>
export default {
  props: {
    list: String
  }
}
</script>

<style>
    li {
        list-style: none;
        padding: 12px 20px;
        color: #fff;
    }
</style>