<template>
    <div>
        <div v-on:click="shake" class="ball black">
            <TheCoverSlot v-if="isCovered"><slot></slot></TheCoverSlot>
            <TheAnswerSlot v-if="!isCovered"><slot></slot></TheAnswerSlot>
        </div>
        <button v-on:click="shake()">Shake It!!!</button>
    </div>

</template>

<script>
    import TheCoverSlot from "./TheCoverSlot";
    import TheAnswerSlot from "./TheAnswerSlot";
    export default {
        components:{
          TheCoverSlot,
            TheAnswerSlot
        },
        name: "TheBall",
        data() {
            return {
                isCovered: true
            }
        },
        methods: {
            shake() {
                this.isCovered = !this.isCovered;
            }
        }
    }

</script>

<style scoped>

</style>