<template>
    <button class="btn" :class="classbtn" :key="namebtn" :type="typebtn">{{namebtn}}</button>
</template>

<script>
export default {

  props: {
    namebtn: String,
    classbtn: String,
    typebtn: String,
    friId: Number,
  }, 

}
</script>

<style>
    .btn {
        border: none;
        padding: 8px 20px;
        border-radius: 9px;
        color: #fff;
        cursor: pointer;
    }
</style>