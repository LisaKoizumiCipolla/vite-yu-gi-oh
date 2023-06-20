<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { Dropdown } from 'bootstrap';

export default {
    name: 'App',

    components:{
      AppHeader,
      AppMain,
      
    }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">

@import "./styles/general.scss";
@import "bootstrap/scss/bootstrap";


</style>
