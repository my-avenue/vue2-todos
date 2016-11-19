<template>
    <li>
        <span :class="{ completed : item.complete }" @click="toggleComplete">{{item.name}}</span>
        <input type="button" value="-" @click="handleRemoveItem">
    </li>
</template>


<script>
    export default{
        props: {
            item: Object
        },
        methods: {
            handleRemoveItem() {
                this.$emit('handleRemoveItem', this.item.id)
            },
            toggleComplete() {
                this.item.complete = !this.item.complete
            }
        }
    }
</script>



<style scoped>
    span {
        color: #3993d8;
        cursor: pointer;
    }

    span.completed {
        color: #ffe0d7;
        text-decoration: line-through;
    }
</style>