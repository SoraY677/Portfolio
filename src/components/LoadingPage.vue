<template>
    <div id="loading-page">
        <li>
        <span 
        v-for="(program_char, index) in program_text"
        :key="index" 
        class="program-char" 
        :style="{animationDelay:index*50+200+'ms'}" 
        v-text="program_char">gheogoaewogos</span>
        </li>
        <p>
            {{formatProgram}}
        </p>
    </div>
</template>

<script>

export default{
    data(){
        return {
            program_text:
                "hogehoge any more Do you know  tyantyan logo"
            
        }
    }
}

</script>

<style>
#loading-page{
    background-color: black;
    color: green;
    height: 100%;
    width: 100%;
    z-index: 10;
    position: absolute;
    left: 0;
    top: 0;
}

@keyframes text-in {
  0% {
    transform: translate(0, 0);
    opacity: 0;
  }
}
.program-char {
  display: inline-block;
  min-width: 0.3em;
  font-size: 2rem;
  animation: text-in .8s cubic-bezier(0.22, 0.15, 0.25, 1.43) 0s backwards;
}

</style>