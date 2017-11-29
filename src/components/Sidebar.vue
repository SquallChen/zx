<template>
  <div id="Sidebar">
    <div class="menu-box">
      <span class="menu-title">校务中心</span>
      <span class="menu-icon"></span>
    </div>
    <ul class="school-affairs-nav">
      <li><a href="#" class="notice" :class="{active: 'notice' === sidebarmemu}" @click="sidebarmemu = 'notice'"><span>校内通知</span></a></li>
      <li><a href="#" class="email" :class="{active: 'email' === sidebarmemu}" @click="sidebarmemu = 'email'"><span>工作邮箱</span></a></li>
      <li><a href="#" class="plan" :class="{active: 'plan' === sidebarmemu}" @click="sidebarmemu = 'plan'"><span>学校周程</span></a></li>
      <li><a href="#" class="rules" :class="{active: 'rules' === sidebarmemu}" @click="sidebarmemu = 'rules'"><span>规章制度</span></a></li>
      <li><a href="#" class="classroom-management" :class="{active: 'classroom-management' === sidebarmemu}" @click="sidebarmemu = 'classroom-management'"><span>场室管理</span></a></li>
      <li><a href="#" class="car-management" :class="{active: 'car-management' === sidebarmemu}" @click="sidebarmemu = 'car-management'"><span>车辆管理</span></a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data:function (){
    return {
      sidebarmemu:'',
    }
  },
}
</script>

<style lang="scss">
  #Sidebar{
    display: flex;
    align-items: center;
    flex-direction: column;
    width:166px;
    margin-top:15px;
    color: #808080;
    font-size: 14px;
    >.menu-box{
      display: flex;
      justify-content: space-between;
      padding-top:8px;
      width:136px;
      height:42px;
       border-bottom: 2px solid black;

      >.menu-icon{
        width:25px;
        height:25px;
        display: inline-block;
        background:url('../assets/images/icon2.png') no-repeat -25px 0;
      }
    }
    >.school-affairs-nav{

      >li{
        >.active{
              background-position-x:-90px;
              color:white;
            }
        >a{
          width:90px;
          height:72px;
          display: flex;
          align-items: flex-end;
          text-align: center;
          color: #808080;
          background:url('../assets/images/work_icon.gif') no-repeat;
          &:hover{
            background-position-x:-90px;
            color:white;
          }
          >span{
            display: inline-block;
            width:90px;
            height:21px;
            margin-bottom: 1.5px;
          }
        }
        >.email{
          background-position: 0 -360px;
          &:hover{
            background-position-x:-87px;
          }
        }
        >.email.active{
          background-position: -87px -360px;
        }
        >.plan{
          background-position: 0 -144px;
        }
        >.plan.active{
          background-position: -90px -144px;
        }
        >.rules{
          background-position: 0 -216px;
        }
        >.rules.active{
          background-position: -90px -216px;
        }
        >.classroom-management{
          background-position: 0 -288px;
        }
        >.classroom-management.active{
          background-position: -90px -288px;
        }
        >.car-management{
          background-position: 0 -457px;
          &:hover{
            background-position-x:-89px;
          }
        }
        >.car-management.active{
          background-position: -89px -457px;
        }
      }
    }
  }
</style>