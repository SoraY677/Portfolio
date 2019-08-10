<!--TopPage.Vue-->
<template>
    <div id="head-card">
        <div id="title">
        <div id="title-name">TenYDGB</div>
        <div id="title-job">Programmer</div>
        </div>
        <describe/>
    </div> 
</template>

<script>

import describe from "./TipingKeysPrinter"

export default{
    name:"HeadCard",
    components:{
        describe
    }
}
</script>

<style>

    #head-card{
        margin-top:250px;
    }

    #head-card #title{
        width:80%;
        margin:auto;
    }

    #head-card #title #title-name{
        font-size:140px;
        
    }

    #head-card #title #title-job{
        font-size:40px;
        transform:translateY(-80%);
        
    }

    #head-card #title #title-job::before,#title-job::after{
        position:absolute;
        width:100%;
        top:0;
        content:"";
        font-size:1;
    }
    #head-card #title #title-job::before{
        left:0;
        width:40%;
        animation: border-extend 2.5s cubic-bezier(0,0, 1, 1) 0s backwards normal;
        border-top:solid 1px #809bff;

    }
    #head-card #title #title-job::after{
        left:40%;
        width:40%;
        animation: border-extend 2.5s cubic-bezier(0,0, 1, 1) 1s backwards normal;
        border-top:solid 1px #2e2e2e;

    }

    @keyframes border-extend{
        0%{width:0%;}
        40%{width:40%;}
    }
</style>