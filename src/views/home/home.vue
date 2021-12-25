<template>
  <div>
    <NavBar class="nav-home"><div slot="center">购物街</div></NavBar>
   <HomeSwiper :banner="banner" />
    <RecommendView :recommends="recommend"/>
  </div>


</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";

import {getHomeMultidata} from "network/home";

export default {
  name: "home",
  components:{
    NavBar,
    HomeSwiper,
    RecommendView
  },
  data(){
    return {
      banner:[],
      recommend:[],
      keywords:[],
      dKeyword:[]
    }
  },
  created() {
    //请求多个数据
    getHomeMultidata().then(res =>{
      //console.log(res);
      //this.result = res;
      this.banner = res.data.banner.list;
      this.recommend = res.data.recommend.list;
      this.keywords = res.data.keywords;
      this.dKeyword = res.data.dKeyword;

    })
  }
}
</script>

<style scoped>
.nav-home{
  background-color: var(--color-tint);
  color: #f6f6f6;
}
</style>
