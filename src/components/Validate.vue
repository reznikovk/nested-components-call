<template>
    <div class="validate">
        <h2>Validate ({{ name }})</h2>
        <button @click="validate">Run</button>
        <div>
            <slot/>
        </div>
    </div>
</template>

<script>

const componentName = "Validate";

export default {
    name: componentName,
    props: ['name'],
    methods: {
        nestedCall (_children) {
            _children.forEach((child) => {
                if (componentName === child.$options.name) {
                    child.validate();
                } else {
                    this.nestedCall(child.$children)
                }
            })
        },
        validate() {
            this.printName()
            this.nestedCall(this.$children)
        },
        printName() {
            console.log(this.name)
        }
    }
}
</script>

<style scoped>
    .validate {
        border: 2px solid black;
        padding: 1rem;
    }
</style>
