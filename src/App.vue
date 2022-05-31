<template>
  <div id="app">
    <HeaderView/>
    <router-view/>
    <FooterView/>
  </div>
</template> 

<script>
// @ is an alias to /src
import HeaderView from '@/components/HeaderView.vue'
import FooterView from '@/components/FooterView.vue'
export default {
  name: 'App',
  components: {
    HeaderView,
    FooterView,
  }
}
</script>

<style>
@import url("./assets/css/main.css");
/*@import url("./assets/css/card-list.css");*/
</style>