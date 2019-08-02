<!--StateController.Vue-->
<template>
  <!-- ページ遷移を管理(this.page_state)-->

  <div id="state-controller">
    <div v-bind:is="transComponents"></div>
  </div>
</template>

<script>
import TopPage from "./TopPage.vue"; 

export default {
  name:"state-contoroller",
  data(){
    return{
      page_state : 0
    }
  },
  components: {
    /*コンポーネント一覧 */
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