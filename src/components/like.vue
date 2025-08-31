<template>
    <div><i @click="getlike()" v-bind:class="[isActive ? activeClass : passiveClass]"></i></div>
</template>
<script>
export default{
  data: function(){
    return{
     isActive: true,
     hasError: false,
     activeClass: 'far fa-heart',
     passiveClass: 'fas fa-heart',
    }
  },
  methods: {
   getlike: function(){
      this.isActive=!this.isActive
   }
    
  },
}
</script>

<style scoped>

</style>