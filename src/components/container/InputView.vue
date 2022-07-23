<template>
    <input :value="valuemodel" @input="$emit('input', $event.target.value)" :type="typeinput" class="formcontrol" :class="classinput" :placeholder="sms">
</template>

<script>
export default {
  emits: [
    "input",
  ],

  props: {
    sms: String,
    typeinput: String,
    classinput: String,
    valuemodel: String,
  },

}
</script>

<style>
    .formcontrol {
        width: 100%;
        padding: 10px 20px;
        box-sizing: border-box;
        margin-bottom: 10px;
        border: none;
        outline: none;
    }
    .ml {
      margin-left: 3px;
    }
</style>