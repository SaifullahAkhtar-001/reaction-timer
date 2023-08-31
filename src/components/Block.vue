<template>
    <p v-if="!showBlock"
        class="mt-12 cursor-pointer font-semibold w-[400px] rounded-xl border-2 border-teal-600 bg-transparent text-teal-600 text-center p-[100px] m-auto">
        click the block asap it appears</p>
    <div v-if="showBlock" @click="stopTimer"
        class="mt-12 text-xl cursor-pointer font-semibold w-[400px] rounded-xl bg-teal-600 text-white text-center p-[100px] m-auto">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 11
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }

}
</script>

<style></style>