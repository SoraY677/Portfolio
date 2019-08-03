<!--StateController.Vue-->
<template>
  <!-- ページ遷移を管理(this.page_state)-->

  <div id="state-controller" >
    <LoadPage/>
    <HamburgerMenu/>
    
     <div v-bind:is="transComponents"></div>
  </div>
</template>

<script>
import LoadPage from "./LoadingPage";
import TopPage from "./ToppageComponents/TopPage.vue"; 
import HamburgerMenu from "./HamburgerMenu";

export default {
  name:"state-contoroller",

  data(){
    return{
      page_state : 0
    }
  },

  components: {
    /*ページごとのコンポーネント*/
    //*ページのコンポーネントを制作したらここに追加する
    LoadPage,
    HamburgerMenu,
    "pagestate-0" :TopPage
  },
  
  computed:{
    //コンポーネント遷移
    transComponents: function(){
      return "pagestate-" + this.page_state;
    }
  }
}
</script>

<style>

</style>