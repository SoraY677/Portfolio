<template>
    <div class="hamburger-navigation" v-bind:class="{open:menu_switch}">
        <div id="hamburger-trigger" v-on:click="switchHamburgerMenu()">
        </div>
        <div id="hamburger-menu">
            <ul>
                <li>aaa</li>
                <li>bbb</li>
                <li>ccc</li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {

    name:"hamburger-navigation",
    data(){
        return{
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
        }
    }
}
</script>

<style>
    .hamburger-navigation{
        z-index: 5;/*最前面*/
        transition:all 120ms 0s ease;
        position: fixed;
        top:0;
        left:0;
    }

    .open{
       transform: translateX(200px);
    }

    /* ハンバーガートリガー */
    .hamburger-navigation #hamburger-trigger{

        width:80px;
        height:80px;
        background-color:#a5a4a4;
        
    }

    /* ハンバーガーメニュー本体 */
    .hamburger-navigation #hamburger-menu{
        position: absolute;
        left:0;
        top:0;
        width:200px;
        background-color:blue;
        transform: translateX(-200px);
    }

</style>