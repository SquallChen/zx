<template>
  <div class="container">
      <Topbar />
      <div>
        <Sidebar />
        <Content />
      </div>
      <Footer />
  </div>
</template>


<script>
import 'normalize.css'
import './assets/reset.css'
import Topbar from './components/Topbar'
import Sidebar from './components/Sidebar'
import Content from './components/Content'
import Footer from './components/Footer'

export default {
  name: 'app',
  data: function () {
    return {
      text: '你好！！！'
    }
  },
  components: {Topbar, Sidebar, Content, Footer}
}
</script>

<style lang="scss">
  .container {
     height: 100%;
     display: flex;
     flex-direction: column;
}
</style>
