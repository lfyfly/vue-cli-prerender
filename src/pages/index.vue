<template>
  <div class="index">
    <h3>{{msg}}</h3>
    <router-link to="/about">to about</router-link>
  </div>
</template>

<script>
export default {
  name: 'index',
  data () {
    return {
      msg: 'this is from index.vue'
    }
  }
}
</script>

<style lang='scss' scoped>
.index{

}
</style>
