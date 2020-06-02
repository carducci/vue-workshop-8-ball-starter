<template>
    <div class="answer-slot">{{ getAnswer() }}</div>
</template>

<script>
    export default {
        name: "TheAnswerSlot",
        methods: {
            getAnswer() {
                const answers = ["Yes", "No", "Ask Again", "Not today!"];
                return answers[Math.floor(Math.random() * answers.length)];
            }
        }
    }
</script>

<style scoped>

</style>