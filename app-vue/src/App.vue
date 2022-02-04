<template>
  <div>
    <Header/>
    <Corpo/>
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import Corpo from './components/Corpo.vue'
export default {
  name:'App',
  components:{
    Header,
    Corpo
  }
}
</script>
