<!--TopPage.Vue-->
<template>
    <div id="head-card">
        <div id="top-head-img-layer" class="top-head-animation"><img src="../../assets/Icon.jpg"></div>
        <div id ="top-head-title-layer">
            <div id="top-head-myname" class="top-head-animation"><span>TenYDGB</span></div>
            <div id="top-head-overwrite" class="top-head-animation">
                <span>MyPortfolio</span>
                </div>
        </div>
    </div> 
</template>

<script>
export default{

}
</script>

<style>
#head-card{
    width:80%;
    min-width:500px;
    margin:auto;
    overflow: hidden;
    display:flex;
    margin-top:20px;
}

#head-card #top-head-img-layer{
    float:left;
    margin:auto;
    height:300px;
    display: inline-flex;
    animation: fadein 0.5s ease 0.5s 1 forwards;
    overflow: hidden;
}

#head-card #top-head-img-layer img{
    object-fit: cover;
    border-radius:50%;
    height:100%;
}
#head-card #top-head-title-layer{
    float:left;
    width:50%;

}

#head-card #top-head-title-layer #top-head-myname{
    width :100%;
    height:50%;
    animation: fadein 0.5s ease 1.0s 1 forwards;
}
#head-card #top-head-title-layer #top-head-myname span{
    font-family: 'Sitka Display',cursive;
    position :absolute;
    font-size: 48px;
    border-bottom:1px #2e2e2e solid;
    width:100%;
    text-align: center;
    bottom:0;
}

#head-card #top-head-title-layer #top-head-overwrite{
    width:100%;
    height:50%;
    animation:fadein 0.5s ease 1.5s 1 forwards;
}

#head-card #top-head-title-layer #top-head-overwrite span{
    font-family: 'Sitka Display',cursive;
    position :absolute;
    font-size:32px;
    width:100%;
    text-align: right;
    transform: translateX(-20px);
    Top:0;
}

#head-card #top-head-title-layer #top-head-overwrite p{
    font-family: 'Sitka Display',cursive;
    position :absolute;
    width:100%;
    text-align: right;
    transform: translateX(-20px);
    Top:0;
    animation:fadein 0.5s ease 1.8s 1 forwards;
    opacity:0;
}

.top-head-animation{
    opacity: 0;
}

@keyframes top-head-img{
    0%{

    }

}

@keyframes fadein{

    0%{
        opacity:0;
    }

    100% {
        opacity: 1;
        transform:translateX(10px);
    }
}

</style>