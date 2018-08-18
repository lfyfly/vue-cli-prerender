<template>
  <div class="about">
    <h3>{{msg}}</h3>
    <router-link to="/">to index</router-link>
  </div>
</template>

<script>
export default {
  name: 'about',
  data () {
    return {
      msg: 'this is from about.vue'
    }
  }
}
</script>

<style lang='scss' scoped>
.about{

}
</style>
