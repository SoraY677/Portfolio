<template>
    <div id="hamburger-navigation" v-bind:class="{open:menu_switch}">
        <div id="hamburger-trigger" v-on:click="switchHamburgerMenu()">
            <!-- メニューの画像をメニューの状態によって変える -->
            <img v-if="menu_switch" src="./../assets/Interface-img/uparrow.png">
            <img v-else src="./../assets/Interface-img/downarrow.png">
            <p>menu</p>
        </div>
        <div id="hamburger-menu">
            <ul>
                <li class="menu-item"
                 v-for="(menu_item,menu_i) in menu_list" 
                 :key="menu_i" 
                 v-on:click="changePagestate(menu_i)">
                 {{menu_item}}
                 </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {

    name:"hamburger-navigation",
    data(){
        return{
            menu_list:[
                "Top",
                "Profile",
                "Skills",
                "Products"
            ],
            menu_switch:false,//ハンバーガーメニューの状態[true:open,false:close]
        }
    },
    methods:{
        //ハンバーガーメニューが押された時に
        //開いていたら閉める
        //閉めていたら開ける
        switchHamburgerMenu:function(){
            if(this.menu_switch == true)//開いていた時
                this.menu_switch = false;
            else if(this.menu_switch == false)//閉めていた時
                this.menu_switch = true;
        },

        //与えられたページ番号に応じて
        //ページ遷移を行い．
        //ハンバーガーメニューを閉じる
        changePagestate: function(pagestate){
            this.$parent.page_state = pagestate;
            this.menu_switch = false;
        }
    }
}
</script>

<style>
    #hamburger-navigation{
        z-index: 5;
        transition:all 120ms 0s ease;
        position: fixed;
        width:100%;
        top:0;
        left:0;
    }

    .open{
       transform: translateY(60px);
    }

    /* ハンバーガートリガー */
    #hamburger-navigation #hamburger-trigger{
        width:65px;
        height:65px;
        background-color:white;
        border:solid 2px #2e2e2e;
        border-radius:50%;
        position:absolute;
        text-align: center;
        left :20px;
        top:10px;
        cursor: pointer;
        
    }

    #hamburger-navigation #hamburger-trigger img{
        width:60%;
        padding :10% 0 0 0;
        left:10%;
        margin:auto;
    }

    #hamburger-navigation #hamburger-trigger p{
        padding:0;
        margin:0;
        font-size:16px;
        font-weight: bold;
        top:65%;
        width:inherit;
        font-family:'Lucida Console','Courier','monospace';
        position:absolute;
    }

    /* ハンバーガーメニュー本体 */
    #hamburger-navigation #hamburger-menu{
        position: absolute;
        left:0;
        top:0;
        width:100%;
        transform: translateY(-60px);
    }

    #hamburger-navigation #hamburger-menu ul{
        width:80%;
        padding : 10px 0px 10px 0px;
        margin:auto;
        text-align: center;
    }

    #hamburger-navigation #hamburger-menu ul li.menu-item{
        list-style: none;
        display:inline;
        margin: 2px 10px 2px 10px;
        font-size:32px;
        cursor: pointer;
    }

</style>