<template>
    <div class="ball black">
    <div class="answer-slot">{{ getAnswer() }}</div>
    </div>
</template>

<script>
    export default {
        name: "TheBall",
        data() {
            return {
            }
        },
        methods: {
            getAnswer() {
                Array.prototype.random = function () {
                    return this[Math.floor(Math.random()*this.length)];
                }
                const answers = ["one", "two", "three"];
                return answers.random();
            }
        }
    }
    //Put in our answers
    //A way to shake

</script>

<style scoped>

</style>