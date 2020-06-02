<template>
    <div class="answer-slot">{{ getAnswer() }}</div>
</template>

<script>
    export default {
        name: "TheAnswerSlot",
        methods: {
            getAnswer() {
                const answers = ["Yes", "No", "Ask Again", "Not today!"];
                const answer =  answers[Math.floor(Math.random() * answers.length)];
                this.$emit("answered",answer);
                return answer;
            }
        }
    }
</script>

<style scoped>
    .answer-slot {
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: absolute;
        margin: -200px 0 0 -200px;
        border-radius: 50%;
        width: 60%;
        height: 60%;
        background: #1a529a;
        left: 70%;
        font-family: Helvetica;
        top: 70%;
        text-align: center;
        color: rgba(255, 255, 255, 0.57);
        line-height: 1.25;
        font-size: 23px;
        -moz-box-shadow: inset 0 0 10px #000000;
        -webkit-box-shadow: inset 0 0 10px #000000;
        box-shadow: inset 0 0 50px #000000;
    }
</style>