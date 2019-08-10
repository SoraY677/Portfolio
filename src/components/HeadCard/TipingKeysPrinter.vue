<template>
    <div id="loading-page">
        <!-- {{updateProgramTextLength()}} -->
        <li v-for="(program_text,program_text_line) in program_texts" :key="program_text_line" class="program-one-text">
        <span v-for="(program_char, index) in program_texts[program_text_line]" :key="index" 
        class="program-char" :style="{animationDelay:(index + 15*program_text_line)*50+2050+'ms'}" v-text="program_char"></span>
        </li>
        <!-- {{changeProgramPage()}} -->
    </div>
</template>

<script>

export default{
    data(){
        return {
            program_texts:[
                "Thank you for visit my portfolio page!",
                "My name is  \"Sora Yamaguchi\"",
                "This Page created in 2019.08.07",
                "Powered by HTML5,CSS,JavaScript,and Vue.js. I appreciate for those well..."
            ],
            //それぞれのプログラム文の単語合計
            //使い方は updateProgramTextLength() 参照
            program_texts_length:[]
        }
    },
    methods:{
        /* updateProgramTextLength */
        //program_texts[0]:24文字
        //program_texts[1]:30文字
        //のとき
        //program_texts_length[0]:0
        //program_texts_length[1]:24
        //program_texts_length[2]:54(24+30)
        updateProgramTextLength:function(){

            for(let i = 0; i < this.program_texts.length+1; i++){
                this.program_texts_length[i] = 0;//初期化
                for(let j=0; j < i; j++){
                    this.program_texts_length[i] += this.program_texts[j].length;//それぞれのプログラム文に加算
                }
            }

        },

        changePageState0to1:function(){
            this.$parent.page_state = 1;
        },
    },
    mounted:function(){
            const timeout = 50 * this.program_texts_length[this.program_texts_length.length-1];
            setTimeout(this.changePageState0to1,timeout);
    }
}

</script>

<style>
#loading-page{
    padding:1%;
    z-index: 10;
    left: 0;
    top: 0;
    word-wrap: break-word;
    font-family: 'arial narrow',sans-serif;
}

.program-char {
  display: inline-block;
  min-width: 0.3em;
  font-size: 2rem;
  animation: text-in .0s cubic-bezier(0.22, 0.15, 0.25, 1.43) 0s backwards;
}
@keyframes text-in {
  0% {
    transform: translate(0, 0);
    opacity: 0;
  }
}

li.program-one-text{
    list-style: none;
}

</style>