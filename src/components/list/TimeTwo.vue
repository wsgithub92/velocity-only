<template>
  <div class="timeeTwo-wrapper">
    <p>{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: "TimeTwo",
  props:{
    name:{
      default:'defalue'
    }
  }
}
</script>

<style scoped>
.timeeTwo-wrapper{
  border: 1px solid cyan;
}

</style>
