<template>
    <div>
        <div v-on:click="shake" class="ball black">
            <div class="cover-slot"><slot></slot></div>

        </div>
        <button v-on:click="shake()">Shake It!!!</button>
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

</script>

<style scoped>

</style>