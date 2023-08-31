<template>
    <p class= "text-teal-600 mt-8 font-semibold font-lg underline">Your response time is <span class="text-4xl">{{ score }}</span>ms</p>
</template>

<script>
export default {
    props: ['score']
}
</script>
