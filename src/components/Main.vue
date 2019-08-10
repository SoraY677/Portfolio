<template>
    <div id="main">
        <HamburgerMenu page_state/>
        <StateController page_state/>
        <Fotter/>
    </div>
</template>

<script>

import StateController from "./StateController"
import HamburgerMenu from "./HamburgerMenu"
import Fotter from "./Fotter"

export default {
    data(){
        return{
            page_state : 0
        }
    },
    components:{
        StateController,
        HamburgerMenu,
        Fotter
    },
    methods:{
        hoge : function(){
            console.log(window.parent.screen);
        }
    }
}
</script>

