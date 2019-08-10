<!--StateController.Vue-->
<template>
    <!-- ページ遷移を管理(this.page_state)-->
        <div id="state-controller" >
        <!-- 自動で画面を変える -->
        <!-- {{autotransPagestatetoNext}} -->
        {{changePagestateSelectedMenu()}}
        <div v-bind:is="transComponents" class="trans-screen"></div>
    </div>
</template>

<script>
import HeadCard from "./HeadCard/HeadCard.vue"; 
import ProfileCard from "./ProfileCard/ProfileCard";
import SkillsCard from "./SkillsCard/SkillsCard"
import ProductsCard from "./ProductsCard/ProductCard"

export default {
  name:"state-contoroller",

  data(){
    return{
      page_state : 2
    }
  },
  components: {
      /*ページごとのコンポーネント*/
      //*ページのコンポーネントを制作したらここに追加する
      "pagestate-0" :HeadCard,
      "pagestate-1" :ProfileCard,
      "pagestate-2" :SkillsCard,
      "pagestate-3" :ProductsCard

    
  },
  methods:{
    addPagestatetoNext:function(){
      this.page_state++;
      //TODO: 
      //コンポーネントの数よりページの遷移数の方が大きかった場合はページの遷移を0に
      if(this.page_state > this.page_list.length)this.page_state = 0;
      console.log("現在のページ状態:" + this.page_state);
    },

    changePagestateSelectedMenu(){
      this.page_state = this.$parent.page_state;
    }
    
    
  },
  computed:{
    //コンポーネント遷移
    transComponents: function(){
      return "pagestate-" + this.page_state;

    },
    //自動で画面を更新するようにsetInterval
    autotransPagestatetoNext:function(){
      setInterval(this.addPagestatetoNext,10*1000);
    }
    
  }
}
</script>

<style>
#state-controller{
}

.trans-screen{
    opacity:1;
}


</style>