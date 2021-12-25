<template>
    <div class="tab-bar-item" @click="isClick">
        <div v-if="!isActive"><slot name="item-icon"></slot></div>
        <div v-else><slot name="item-icon-active"></slot></div>
        <div :style="activeStyle"><slot name="item-text"></slot></div>
    </div>
</template>

<script>
export default {
  name: "tabbar-item",
  props:{
    path:String,
    activeColor:{
      type:String,
      default:"pink"
    }
  },
  // data(){
  //   return {
  //     isActive: false
  //   }
  // },
  computed:{
    isActive(){
      return this.$route.path.indexOf(this.path) !== -1;
    },
    activeStyle(){
      return this.isActive ? {color:this.activeColor} : {};
    }

  },
  methods:{
    isClick(){
      //console.log("click");
      this.$router.replace(this.path);
    }
  },
  activated() {
    console.log("激活了");
  }
}
</script>

<style scoped>
.tab-bar-item{
  flex: 1;
  text-align: center;
  height: 49px;
}
.tab-bar-item img{
  width: 24px;
  height: 24px;
}
.active{
  color: pink;
}
</style>
