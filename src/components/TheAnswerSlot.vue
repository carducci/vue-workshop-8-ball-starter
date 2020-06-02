<template>
    <div class="answer-slot">{{ getAnswer() }}</div>
</template>

<script>
    export default {
        name: "TheAnswerSlot",
        data() {
            return { answer: null }
        },
        methods: {
            getAnswer() {
                Array.prototype.random = function () {
                    return this[Math.floor(Math.random() * this.length)];
                }
                const answers = ["Yes", "No", "Ask Again", "Not today!"];
                return answers.random();
            }
        }
    }
</script>

<style scoped>

</style>