<template>
  <div class="tab-control">
    <div v-for = "(item,index) in titles" class="tab-control-item" :class="{active:index === currentIndex}" @click="itemClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data(){
    return{
      currentIndex:0,
    }
  },
  methods:{
    itemClick(index){
      this.currentIndex = index;
      this.$emit('tabclick',index)
    }
  }
};
</script>

<style>
.tab-control {
  display: flex;
  text-align: center;
  font-size: 15px;
  height: 44px;
  line-height: 40px;
  background-color: #fff;
  position: sticky;
  /* top:40px; */
  z-index: 9;
}
.tab-control-item {
  flex: 1;
}
.active{
  color: #ff5777;
}
.active span{
  border-bottom: 3px solid #ff8198;
  padding: 5px;
}

</style>
