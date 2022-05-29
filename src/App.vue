<template>
    <h2>Memory Game</h2>
    <button @click="shuffleImg()">New Game</button>

    {{ shuffleImg() }}

    <div v-for="img in shuffeledImg" :key="img.id">
        <SingleCard :img="img" :cover="cover"/>
    </div>
    <span>Turns: {{ turns }}</span>
</template>

<script>
import SingleCard from "./components/SingleCard";

export default {
    name: "App",
    components: { SingleCard },
    data() {
        return {
            img: [
                {
                    src: "./img/planet1.png",
                },
                {
                    src: "./img/planet2.png",
                },
                {
                    src: "./img/planet3.png",
                },
                {
                    src: "./img/planet4.png",
                },
                {
                    src: "./img/planet5.png",
                },
                {
                    src: "./img/planet6.png",
                },
            ],
            shuffeledImg: [],
            cover: "./img/cover.png",
            turns: 0,
        };
    },
    methods: {
        shuffleImg() {
            this.shuffeledImg = [...this.img, ...this.img] // clone the img twice
                .sort(() => Math.random() - 0.5) // sort the cloned img randomly
                .map((img) => ({ ...img, id: Math.random() })); // return the shorted array by adding id property

            this.turn = 0;
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
