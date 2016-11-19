<template>
    <div>
        <ul>
            <todo-item  v-for="item in itemlist" :item="item" @handleRemoveItem="handleRemoveItem"></todo-item>
        </ul>
    </div>
</template>


<script>
    import TodoItem from './TodoItem'
    export default{
        props: {
            itemlist: Array
        },
        methods: {
            handleRemoveItem: function (itemid) {
                this.$emit('handleRemoveItem', itemid)
            }
        },
        components: {
            TodoItem
        }
    }
</script>

<style scoped>
    ul {
        list-style-position: inside;
    }
</style>

