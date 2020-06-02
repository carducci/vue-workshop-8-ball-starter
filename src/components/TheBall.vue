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
    .ball {
        width: 400px;
        height: 400px;
        position: absolute;
        left: 50%;
        top: 50%;
        margin: -200px 0 0 -200px;
        border-radius: 50%;
    }




    .ball.black {
        background: radial-gradient(
                circle at 50% 120%,
                #323232,
                #0a0a0a 80%,
                #000000 100%
        );
    }

    .ball:before {
        content: "";
        position: absolute;
        background: radial-gradient(circle at 50% 120%, rgba(255, 255, 255, 0.5), rgba(255, 255, 255, 0) 70%);
        border-radius: 50%;
        bottom: 2.5%;
        left: 5%;
        opacity: 0.6;
        height: 100%;
        width: 90%;
        -webkit-filter: blur(5px);
        z-index: 2;
    }
    .ball:after {
        width: 100%;
        height: 100%;
        content: "";
        position: absolute;
        top: 5%;
        left: 10%;
        border-radius: 50%;
        background: radial-gradient(circle at 40% 46%, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.8) 10%, rgba(255, 255, 255, 0) 17%);
        -webkit-transform: translateX(-80px) translateY(-90px) skewX(-20deg);
        transform: translateX(-80px) translateY(-90px) skewX(-20deg);
        -webkit-filter: blur(10px);
    }

    .ball.brown {
        background: radial-gradient(
                circle at 50% 120%,
                #964500,
                #c56400 80%,
                #c36300 100%
        );
    }
    .ball.red {
        background: radial-gradient(
                circle at 50% 120%,
                #960000,
                #c50000 80%,
                #c30000 100%
        );
    }

    .ball.black {
        background: radial-gradient(
                circle at 50% 120%,
                #323232,
                #0a0a0a 80%,
                #000000 100%
        );
    }

    .ball.green {
        background: radial-gradient(
                circle at 50% 120%,
                #063a00,
                #1f9a00 80%,
                #00a02a 100%
        );
    }

    .ball.orange {
        background: radial-gradient(
                circle at 50% 120%,
                #d88200,
                #fb9700 80%,
                #a76400 100%
        );
    }

    .ball.purple {
        background: radial-gradient(
                circle at 50% 120%,
                #0f0927,
                #6b46c3 80%,
                #1e123c 100%
        );
    }
    .ball.yellow {
        background: radial-gradient(
                circle at 50% 120%,
                #ecca33,
                #fdd835 80%,
                #e2c236 100%
        );
    }

    .ball.blue {
        background: radial-gradient(
                circle at 50% 120%,
                #053196,
                #032cf4 80%,
                #032cf4 100%
        );
    }

</style>