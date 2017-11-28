<template>
  <div id="Topbar">
    <div class="header">
      <div class="headerlogo"></div>
      <div class="teacherinfo">
        <div class="qrcode"></div>
        <div class="welcome">
          <p>您好，叶晓辉 任课教师</p>
          <p>角色：教师</p>
        </div>
      </div>
    </div>
    <div class="navigation">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Topbar'
}
</script>

<style lang="scss">
  #Topbar{
    height:110px;
    color: red;
    background: url('../assets/images/header_bg.jpg');

    >.header{
      height:78px;
      display: flex;
      justify-content: space-between;

      >.headerlogo{
        width:700px;
        height:78px;
        margin-left: 20px;
        background: url('../assets/images/logo.png')
      }

      >.teacherinfo{
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: right;
        margin-right:39px;
        >.qrcode{
          width:65px;
          height:65px;
          background: url('../assets/images/zhix.jpg')
        }
        >.welcome{
          width:148px;
          height:52px;
          color:#6e4c1c;
          font-size: 14px;
          font-weight: bold;
          margin-top:26px;
          margin-left:6px;

          >p{
            line-height: 24px;
          }
        }
      }
    }
  }
</style>