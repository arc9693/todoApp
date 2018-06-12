<template lang="html">
  <div class="todoAdd">
    <input type="text" v-model="item" placeholder="Add todo item.."/>
    <button type="button" name="button" v-on:click="Addthis" class="teal">Add</button>

  </div>
</template>

<script>
export default {
  name:'todoAdd',
  data(){
    return{
    item:'',
  }
  },
  methods:{
    Addthis(){
      this.$emit("todo:add",this.item);
      this.item='';
    }
  }
}
</script>

<style lang="css" scoped>
   input{
     padding:8px;border:none;border-bottom:1px solid skyblue;border-top:1px solid skyblue;width:80%;

   }
   button{border:none;padding:8px 16px;overflow:hidden;text-decoration:none;color:inherit;text-align:center;cursor:pointer;
   }
   .teal{color:#fff!important;background-color:#009688!important}
  button:hover{color:#000!important;background-color:#ccc!important}

</style>
