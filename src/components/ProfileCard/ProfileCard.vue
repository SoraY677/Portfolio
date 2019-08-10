<template>
    <div id="profile-card" class="base-layout">
        <h1>Profile</h1>
        <table>
            <tr v-for="(author_data,author_data_i) in author_datas" :key="author_data_i">
                <td>{{author_data[0]}}</td>
                <td>{{author_data[1]}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    data(){
        return{
            author_datas:{
                name:["氏名","山口宙来(YAMAGUCHI Sora)"],
                year_and_gend:["年齢・性別","20歳・男性"],
                belong:["所属","東京都市大学　メディア情報学部 情報システム学科 3年"],
                certificate:["所持する資格","ITパスポート・基本情報技術者・応用情報技術者"],
                hoby:["趣味","プログラミング・クイズ・絵を描く・愛犬と遊ぶ"]

            }
        }
    }
}
</script>


<style>
    #profile-card table{
        font-size:24px;
        animation:intro-animation 1.0s ease 0s 1;
        overflow:scroll;
        height:60%;
        width:90%;
    }

    @keyframes intro-animation {
        0%{transform: translateY(-20%);
        opacity:0;}
        100%{transform: translateY(0);
        opacity:1;}

    }
    #profile-card table tr td{
        padding:10px;
    }
</style>


