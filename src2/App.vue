<template>
  <div id="app">
    <div id="appTop">
      <Top/>
    </div>
    <div id="appBody">
      <Body/>
    </div>
    <div id="appFooter">
      <Footer/>
    </div>
  </div>
</template>

<script>
import Top from './components/header/header'
import Body from './components/body/body'
import Footer from './components/footer/footer'

export default {
  name: 'App',
  components: {
    Top,
    Body,
    Footer
  }
}
</script>

<style>

</style>
