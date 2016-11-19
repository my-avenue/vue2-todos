<template>
    <div>
        <input type="text" v-model="newitem" @keyup.enter="handleNewItem"/>
        <input type="button" value="Add" @click="handleNewItem"/>
    </div>
</template>


<script>
    export default{
        data(){
            return{
                newitem:''
            }
        },
        methods:{
          handleNewItem() {
              this.$emit('handleNewItem', this.newitem)
              this.newitem = ''
          }
        }
    }
</script>

