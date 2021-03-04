<template>
    <div class="some">
        <h2>Some</h2>
        <div>
            <slot/>
        </div>
    </div>
</template>

<script>
export default {
    name: "Some"
}
</script>

<style scoped>
.some {
    border: 2px solid red;
    padding: 1rem;
}
</style>
