<template>
  <app-header v-bind:propsdata="str"
            v-on:renew="renewStr"></app-header>
</template>

<script>
import AppHeader from './components/AppHedaer.vue'
/* 싱글파일 컴포넌트에서는 사용 x 재사용성을 위해
 new VUE({
   data : {
     
   }
 });
*/
export default {
  data : function(){
    return {
      str : 'HeaderPropsz'
    }
  },
  components : {
    'app-header' : AppHeader
  },
  methods : {
    renewStr : function(){
      this.str = 'test';
    }
  }
}
</script>

<style>

</style>