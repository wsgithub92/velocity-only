<!--component :is的使用-->
<template>
  <div class="list-wrapper">
    <div class="list-btn" v-for="(item,index) in listName" :key="index"
    @click="listbtnClick(item)">
      {{item.name}}
    </div>
    <!--name是多个组件之间的都存在的props传值-->
    <keep-alive>
      <component :is='activeItem' :name = 'nowName'></component>
    </keep-alive>
  </div>

</template>

<script>
import TimeOne from "@/components/list/TimeOne";
import TimeTwo from "@/components/list/TimeTwo";

export default {
  name: "List",
  components:{
    TimeOne,
    TimeTwo
  },
  data(){
    return{
      listName: [TimeOne,TimeTwo],
      activeItem:'',
      nowName:'',
    }
  },
  mounted() {
    console.log(this.listName)
  },
  methods:{
    listbtnClick(item){
      if(this.activeItem === item) return;
      this.activeItem = item.name;
      switch (this.activeItem){
        case "TimeOne":
          this.nowName = '当前是TimeOne'
          break;
        case "TimeTwo":
          this.nowName = '当前是TimeTwo'
          break;
      }
    }
  }

}
</script>

<style scoped>
.list-wrapper{
  border: 1px solid cornflowerblue;
}
.list-btn{
  padding: 10px 20px;
  border: 1px solid #ff9048;
  display: inline-block;
  cursor: pointer;
}
</style>
