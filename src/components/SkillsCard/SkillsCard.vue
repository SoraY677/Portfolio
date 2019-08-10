<template>
    <div id="skills-card" class="base-layout">
        <h1>Skills</h1>
        <div id="graph-area">
            <ul>
                <li v-for="(one_language,language_i) in languages" :key="language_i">
                    <div class="language-name">{{one_language.name}}</div>
                    <div class="language-graph">
                        <div class="extend-graph" :style="{'max-width':one_language.max_width+'%','background-color':one_language.color}"></div>
                    </div>
                    <div class="language-from" :style="{animationDelay:one_language.max_width * 0.01*2.0+'s'}">from:{{one_language.from}}</div>
                </li>
            </ul>
        </div>
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            /*各言語スキルの詳細 */

            languages :  {
                //言語名:{name:言語名, max_width:経験量(%)}, color:色("#"で指定), from:始めた年
                language_c:{name:"C", max_width:100, color:"#FFFF00",from:2013},
                language_cpp:{name:"C++",max_width:70, color:"#FF9900",from:2014},
                language_java:{name:"Java", max_width:70, color:"#33CC33",from:2017},
                language_kotlin:{name:"Kotlin", max_width:10, color:"#33FF33",from:2019},
                language_python:{name:"Python", max_width:10, color:"#FF0033",from:2019},
                language_JavaScript:{name:"JavaScript", max_width:20, color:"#FFCC33", from:2018},
                language_php:{name:"php", max_width:4,color:"#3333CC",from:2018}
            }
        }
    }
}
</script>


<style>
    #skills-card #graph-area{
        margin-top:30px;
    }

    #skills-card #graph-area li{
        list-style: none;
        margin-top:25px;
        height:30px;
    }
    
    #skills-card #graph-area .language-name{
        font-weight:bold;
        width:10%;
        float:left;
        z-index: 10;
        word-wrap: break-word;
    }

    #skills-card #graph-area .language-graph {
        width:80%;
        height:100%;
        
        float:left;
    }

    #skills-card #graph-area .language-graph .extend-graph{
        height:100%;
        animation:graph-extend-anim 2.5s cubic-bezier(0.29, -0.26, 0.56, 1.4) 0s 1;
        border-radius: 5px;
    }

    @keyframes graph-extend-anim{
        0%{width:0%;}
        100%{width:100%;}
    }

    #skills-card #graph-area .language-from{
        float:right;
        font-style:oblique;
        animation:from-anim 1s ease 0s backwards;
    } 

    @keyframes from-anim{
        0%{opacity:0}
        100%{opacity:1}
    }

</style>

