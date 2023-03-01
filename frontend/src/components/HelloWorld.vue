<template>
    <div class="hello">
        <n-carousel autoplay :show-dots="false">
            <img id="color1" class="carousel-img" />
            <img id="color2" class="carousel-img" />
            <img id="color3" class="carousel-img" />
            <img id="color4" class="carousel-img" />
        </n-carousel>
        <div class="background-section"></div>
        <n-card title="Huge Card" size="huge" class="card centered">
            Card Content
        </n-card>
        <n-card title="Huge Card" size="huge" class="card">
            Card Content
        </n-card>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { NCarousel, NCard } from 'naive-ui'

export default defineComponent({
    name: 'HelloWorld',
    props: {
        msg: String
    },
    components: {
        NCarousel,
        NCard
    }
})
</script>

<style lang="scss">
#color1 {
    background-image: linear-gradient(to right, #335c67, #fff3b0);
}
#color2 {
    background-image: linear-gradient(to right, #fff3b0, #e09f3e);
}
#color3 {
    background-image: linear-gradient(to right, #e09f3e, #9e2a2b);
}
#color4 {
    background-image: linear-gradient(to right, #9e2a2b, #540b0e);
}
.carousel-img {
    width: 100%;
    height: 5000px;
    object-fit: cover;
}
.background-section {
    position: absolute;
    top: 500px;
    width: 100%;
    height: 600px;
    z-index: 0;
    background-color: lightgray;
}
.card {
    --normal-transition-width: 16px;
    --large-card-width: 100%;
    --big-card-width: 1100px;
    --normal-card-height: 350px;
    --long-card-height: 550px;
    --card-height: 350px;
    --nb-cards: 2;

    top: -4700px;
    width: var(--big-card-width);
    height: var(--normal-card-height);
    border-radius: 0px 32px 32px 0px;
    box-shadow: 5px 10px;
    transition: width 0.25s;
    margin-top: 128px;

    &.right {
        --full-transition-width: 400px;
        --small-card-width: 350px;
        --small-card-height: 200px;

        width: 150px;
        height: var(--small-card-height);
        top: 50px;
        right: -100px;
        border-radius: 32px 0px 0px 32px;
        z-index: 1000;
        transition: right 0.25s;

        &:hover {
            right: 0px;
        }
    }

    &:hover {
        width: calc(var(--big-card-width) + var(--normal-transition-width));
    }

    &.large {
        top: 900px;
        width: var(--large-card-width);
        border-radius: 32px;
    }

    &.centered {
        position: relative;
        width: var(--big-card-width);
        margin: auto;
        border-radius: 32px;
        height: var(--long-card-height);
    }
}
</style>
