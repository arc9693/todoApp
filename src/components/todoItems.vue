<template lang="html">
  <div class="todoItems">
     {{todo.name}} <button class="pale-red" @click="removeItem">Remove</button>
  </div>
</template>

<script>
export default {
  name:'todoItems',
  props:['todo'],
  methods:{
   removeItem(){
     this.$emit("todo:remove",this.todo.id);
   }
 }
}
</script>

<style lang="css" scoped>

.todoItems{
   padding:8px;border:2px solid #ffdddd;border-radius:10px;width:100%;margin:5px 0px 5px;text-decoration: none;text-align: left;
}
.pale-red{color:#fff!important;background-color:#f44336!important}
button{border:none;padding:3px 6px;overflow:hidden;text-decoration:none;color:inherit;text-align:center;cursor:pointer;float: right;
}
button:hover{color:#000!important;background-color:#ccc!important}
</style>
