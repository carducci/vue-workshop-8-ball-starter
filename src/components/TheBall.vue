<template>
    <div>
        <div v-on:click="shake" class="ball black">
            <TheCoverSlot><slot></slot></TheCoverSlot>
            <div v-if="!isCovered" class="answer-slot">{{ answer }}</div>
        </div>
        <button v-on:click="shake()">Shake It!!!</button>
    </div>

</template>

<script>
    import TheCoverSlot from "./TheCoverSlot";
    export default {
        components:{
          TheCoverSlot
        },
        name: "TheBall",
        data() {
            return {
                isCovered: true,
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

</script>

<style scoped>

</style>