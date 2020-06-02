<template>
    <div>
        <div class="ball black">
            <div class="answer-slot">{{ answer }}</div>
        </div>
        <button v-on:click="shake">Shake It!!!</button>
    </div>

</template>

<script>
    export default {
        name: "TheBall",
        data() {
            return {
                answer: "Shake to reveal your destiny..."
            }
        },
        methods: {
            getAnswer() {
                Array.prototype.random = function () {
                    return this[Math.floor(Math.random() * this.length)];
                }
                const answers = ["Yes", "No", "Ask Again", "Not today!"];
                return answers.random();
            },
            shake() {
                this.answer = this.getAnswer();
            }
        }
    }

    //A way to shake

</script>

<style scoped>

</style>