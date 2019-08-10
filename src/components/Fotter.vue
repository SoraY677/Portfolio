<template>
    <div id="fotter">
        <ul id="sns-link">
        <li><a href="https://twitter.com/TenYDGB"><img class="sns-item" src="../../src/assets/snslink-img/Twitter_Logo_WhiteOnBlue.png"></a></li>
        <li><a href="https://github.com/SoraY677"><img class="sns-item" src="../../src/assets/snslink-img/GitHub-Mark-64px.png"></a></li>
        <li><a href="https://qiita.com/lastorder0316"><img class="sns-item" src="../../src/assets/snslink-img/qiita-square.png"></a></li>
        </ul>
    </div>
</template>



<style>
    #fotter{
        position:absolute;
        float:right;
        width:100%;
        margin-top:100vh;
        transform: translateY(-100%);
        text-align: right;
        top:0;
        left:0;
        overflow: hidden;
    }

    #fotter ul#sns-link {
        float:right;
    }

    #fotter ul#sns-link li{
        list-style: none;
        margin-right:23px;
        float:left;
    }

    #fotter ul#sns-link li img.sns-item{
        min-width:55px;
        width:55px;
        border-radius:10%;
        
        
    }
</style>
