<template>
    <div>
        <img v-bind:src="cover" alt="cover" />
        <img v-bind:src="img.src" alt="planet" />
    </div>
</template>

<script>
export default {
    props: ['img', 'cover'],
};
</script>

<style></style>
