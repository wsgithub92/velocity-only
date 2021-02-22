<template>
  <div class="timeone-wrapper">
    <p>{{name}}</p>
    <div class="list">
      <p v-for="(item,index) in 10" :key="index+'a'"
      class="list-p" :class="activeIndex === item ? 'active' : ''"
      @click.stop="listClick(item)">{{item}}</p>
    </div>
  </div>

</template>

<script>
export default {
name: "TimeOne",
  props:{
    name:{
      default:'defalue'
    }
  },
  data(){
    return{
      activeIndex:0
    }
  },
  methods:{
    listClick(item){
      this.activeIndex = item;
    }
  }
}
</script>

<style scoped>
.timeone-wrapper{
  border: 1px solid coral;
}
.list{
  display: inline-block;
}
.list-p{
  border: 1px solid darkcyan;
  padding: 10px 20px;
  cursor: pointer;
}
.active{
  background: #ff9048;
  color: white;
}

</style>
