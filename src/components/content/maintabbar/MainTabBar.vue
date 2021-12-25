<template>
  <TabBar>
    <TabBarItem path="/home" active-color="green">
      <img src="~assets/img/tabbar/首页.svg" alt="" slot="item-icon">
      <img src="~assets/img/tabbar/首页-激活.svg" alt="" slot="item-icon-active">
      <div slot="item-text">首页</div>
    </TabBarItem>
    <TabBarItem path="/category" active-color="blue">
      <img src="~assets/img/tabbar/category.svg" alt="" slot="item-icon">
      <img src="~assets/img/tabbar/分类-激活3.svg" alt="" slot="item-icon-active">
      <div slot="item-text">分类</div>
    </TabBarItem >
    <TabBarItem path="/cart" active-color="red">
      <img src="~assets/img/tabbar/购物车空.svg" slot="item-icon" >
      <img src="~assets/img/tabbar/购物车-激活.svg" alt="" slot="item-icon-active">
      <div slot="item-text">购物车</div>
    </TabBarItem>
    <TabBarItem path="/profile" active-color="orange">
      <img src="~assets/img/tabbar/_我的.svg" slot="item-icon">
      <img src="~assets/img/tabbar/我的-激活.svg" alt="" slot="item-icon-active">
      <div slot="item-text">我的</div>
    </TabBarItem>
  </TabBar>
</template>

<script>
import TabBar from 'components/common/tabbar/TabBar'
import TabBarItem from 'components/common/tabbar/tabbar-item'
export default {
  name: "MainTabBar",
  components:{
    TabBar,
    TabBarItem
  }
}
</script>

<style scoped>

</style>
