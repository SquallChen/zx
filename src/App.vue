<template>
  <div class="container">
    <Topbar />
    <div class="main">
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
  html,body{
    min-height: 768px;
    height: 100%;
    min-width:1300px;
    font:12px/24px "hiragino sans gb","Microsoft YaHei", "微软雅黑", SimSun, SimHei, Arial;
  }
  .container {
     min-height: 100%;
     display: flex;
     flex-direction: column;


     >.main {
      flex:1;
      display: flex;
      min-width: 1300px;

      background-color: #e4e4e4;

      }

}

</style>
