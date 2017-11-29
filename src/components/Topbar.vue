<template>
  <div id="Topbar">
    <div class="header">
      <div class="headerlogo"></div>
      <div class="teacherinfo">
        <div class="qrcode"></div>
        <div class="welcome">
          <p>您好，<span>叶晓辉</span><span>任课教师</span></p>
          <p>角色：教师</p>
        </div>
      </div>
    </div>
    <div class="navigation">
      <ul class="leftsidenav">
        <li><a :class="{active: 'school-affairs' === selected}"
        @click="selected = 'school-affairs'">
        <span class="school-affairs"></span>校务</a></li>
        <li><a :class="{active: 'Teaching' === selected}" @click="selected = 'Teaching'"><span class="Teaching"></span>教务</a></li>
        <li><a :class="{active: 'Teacher' === selected}" @click="selected  = 'Teacher'"><span class="Teacher"></span>教师</a></li>
        <li><a :class="{active: 'score' === selected}" @click="selected = 'score'"><span class="score"></span>成绩</a></li>
        <li><a :class="{active: 'system' === selected}" @click="selected = 'system'"><span class="system"></span>系统</a></li>
        <li><a :class="{active: 'morale-ducation' === selected}" @click="selected = 'morale-ducation'"><span class="moral-education"></span>德育</a></li>
      </ul>
      <ul class="rightsidenav">
        <li><a class="commonmenu" @click="selected = 'common'"><span class="common"></span>常用菜单</a></li>
        <li><a class="message" @click="selected = 'mess'"><span class="mess"></span>你有(0)条未读信息</a></li>
        <li><a  @click="selected = 'indexpage'"><span class="indexpage"></span>首页</a></li>
        <li><a @click="selected = 'set'"><span class="set"></span>设置</a></li>
        <li><a class="addressbook" @click="selected = 'addressbook'"><span class="address"></span>通讯录</a></li>
        <li><a @click="selected = 'quit'"><span class="quit"></span>退出</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Topbar',
  data:function (){
    return {
      selected:'indexpage',
    }
  },
  methods: {
       alert(meg){
        alert(this.selected)
      }
      },
}
</script>

<style lang="scss">
  #Topbar{
    height:109px;
    background: url('../assets/images/header_bg.jpg');

    >.header{
      height:77px;
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
        margin-right:37px;
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
          margin-left:10px;

          >p{
            line-height: 24px;

            >span{
              margin-right:8px;
            }
          }
        }
      }
    }
    >.navigation{
      display: flex;
      justify-content: space-between;
      height:32px;
      background: #6e4c1c;

      >ul{
        display: inline-block;

        >li{
          display: inline-block;
          >.active{
                background: url('../assets/images/nav-hover.gif') center bottom no-repeat;
            }
          >a{
            display: inline-block;
            color:white;
            font-size: 14px;
            font-weight: bold;
            margin-left:-3.6px;
            cursor: pointer;
             &:hover{
              background: url('../assets/images/nav-hover.gif') center bottom no-repeat;
            }
          }
        }
      }
      >.leftsidenav{
        margin-left:21px;
        >li{

          >a{
            display: flex;
            justify-content:center;
            align-items: center;
            width:71px;
            height:32px;
            text-align: center;

            >.school-affairs{
              background-position-x: -25px;
            }
            >.Teaching{
              background-position-x: -50px;
            }
            >.Teacher{
              background-position: -25px;
            }
            >.score{
              background-position: -75px -25px;
            }
            >.system{
              background-position-y: -50px;
            }
            >.moral-education{
               background-position-x: -25px;
            }
            >span{
            display: inline-block;
            width:25px;
            height:25px;
            margin-right:3px;
            background:url('../assets/images/icon.png') no-repeat;
             }
          }
        }
      }
      >.rightsidenav{
        margin-right: 40px;
        >li{
          >a{
            display: flex;
            justify-content:center;
            align-items:center;
            width:71px;
            height:32px;
            text-align: center;
            cursor: pointer;
            >span{
              display: inline-block;
              width:25px;
              height:25px;
              margin-right:3px;
            }
            >.common{
              background: url('../assets/images/icon.png') no-repeat -50px -50px;
            }
            >.mess{
              background: url('../assets/images/messge_icon.png') no-repeat 0 2px;
            }
            >.indexpage{
              background: url('../assets/images/icon.png') no-repeat;
            }
            >.set{
              background: url('../assets/images/index_set_icon.png') no-repeat;
            }
            >.address{
              background: url('../assets/images/icon.png') no-repeat -25px -50px;
            }
            >.quit{
              background: url('../assets/images/icon.png') no-repeat -50px -50px;
            }
          }
          >.commonmenu{
              width:99px;
          }
          >.message{
            width:160px;
          }
          >.addressbook{
            width:85px;
          }
        }
      }
    }
  }
</style>