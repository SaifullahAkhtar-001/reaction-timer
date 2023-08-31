<template>
    <p class= "text-teal-600 mt-8 font-semibold font-lg underline underline-offset-4">Your response time is <span class="text-4xl">{{ score }}</span>ms</p>
    <p class= "text-xl text-teal-600 mt-8 font-semibold font-lg ">{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return{
            rank: null
        }
    },
    mounted() {
        if (this.score < 250){
            this.rank = '🐇 Fast'
        }
        else if (this.score < 500){
            this.rank = '🦊 Average'
        }
        else {
            this.rank = '🐢 Slow Af!'
        }
    }
}
</script>
