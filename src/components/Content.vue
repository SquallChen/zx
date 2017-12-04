<template>
  <div id="Content">
    <!-- 左边容器 -->
    <div class="content-left">
    <!-- 最新学校通知 -->
      <div class="new-notice">
        <ul>
          <li class="ultitle"><span>最新学校通知</span><span><a href="#" class="more">更多>></a></span></li>
          <li  v-if="index < 6" v-for = "(ntcdata,index) in noticedata "  :key="ntcdata.index"><span><a href="#">{{ntcdata.notice_title}}</a></span>
          <span class="notice-time">{{ntcdata.release_time}}</span>
          <span class="announcer">{{ntcdata.announcer}}</span></li>
        </ul>
      </div>
      <!-- 最新学生管理 -->
      <div class="new-students-management">
        <ul>
          <li class="ultitle"><span>最新学生管理</span><span><a href="#" class="more">更多>></a></span></li>
          <li  v-if="index < 6" v-for = "(ntcdata,index) in noticedata "  :key="ntcdata.index"><span><a href="#">{{ntcdata.notice_title}}</a></span>
          <span class="notice-time">{{ntcdata.release_time}}</span>
          <span class="announcer">{{ntcdata.announcer}}</span></li>
        </ul>
      </div>
      <!-- 课题(近期公开课) -->
      <div class="new-public-class">
        <ul>
          <li class="pub-ultitle"><span>课题(近期公开课)</span><span class="pub-ultitle-time">时间<a href="#" class="pub-more">更多>></a></span><span class="speaker">授课人</span></li>
          <li  v-if="index < 8" v-for = "(ntcdata,index) in noticedata "  :key="ntcdata.index"><span><a href="#">{{ntcdata.notice_title}}</a></span>
          <span class="pub-time">{{ntcdata.release_time}}</span>
          <span class="pub-announcer">{{ntcdata.announcer}}</span></li>
        </ul>
      </div>
      <!-- 操作纪录 -->
      <div class="Modifyinfo">
        <ul>
          <li class="mod-ultitle"><span class="mod-ultitle-men">操作人</span><span class="mod-ultitle-info">学生信息修改</span><span class="mod-ultitle-time">操作时间</span></li>
          <li>
            <span class="mod-men">super</span>
            <span>调整<span>田昊东的所在班别</span></span>
            <span>2014-01-03</span>
          </li>
          <li>
            <span>super</span>
            <span>调整<span>田昊东的所在班别</span></span>
            <span>2014-01-03</span>
          </li>
        </ul>
      </div>

      <div class="todolist"></div>
    </div>
    <!-- 右边容器 -->
    <div class="content-right">
      <div class="new-remind"></div>
      <div class="colleague"></div>
    </div>
  </div>
</template>



<script>

export default {
  name: 'Contents',
  data:function(){
    return {
      noticedata:'',
      stu_manage:'',
    }
  },
  mounted: function() {
    this.getJsonInfo()
},
methods: {
    getJsonInfo: function() {
        this.$http.get('notice.json').then(function(response){
            /* console.log(response.data.data) */

            //var tempdata = response.data.****
            //this.stu_manage = temp***
            var tempnotice_data = response.data.notice_data
            this.noticedata = tempnotice_data
        }).catch(function(response){
            console.log(response)
            console.log("居然没有弹窗")
        })
    }
    }
}

</script>


<style lang="scss">
  #Content{
    justify-content: space-between;
    background: white;
    flex-grow: 1;
    margin-top:15px;
    display: flex;
    padding-top:19px;
    padding-left:11px;
    color: #4a4949;

    ul{
      border: 2px solid #d0c7aa;
      border-left: 3px solid #d0c7aa;
      border-right: 3px solid #d0c7aa;

    >li{
      height:26px;
      padding-left:14px;


      >span{

        >a{
        color: #4a4949;
        &::visited{
          color: #4a4949;
            }
         }
      }


      >.notice-time{
            float:right;
            text-align: center;
            display: inline-block;
            width:97px;
            height:26px;
            border-left: 2px solid #d0c7aa;
            color: #4a4949;
        }
      >.announcer{
            float:right;
            text-align: center;
            display: inline-block;
            width:64px;
            height:26px;
            border-left: 2px solid #d0c7aa;
            color: #4a4949;
        }
    }
    >.ultitle{
      padding-left: 10px;
      font-weight: bold;
      color: #644635;
      background: url('../assets/images/table_tittle.jpg') repeat-x;

        >span{

          >.more{
            float:right;
            text-align: center;
            display: inline-block;
            width:97px;
            height:26px;
            border-left: 2px solid #d0c7aa;
            color: #4a4949;
            &:hover{
              color: #644635;
            }
          }
        }
        a{
        color: #644635;
        &:hover{
          text-decoration: underline;
        }
      }
    }
    }
/* *************左边容器 *******************/
    >.content-left{
      display: flex;
      flex-wrap: wrap;
      flex-grow:1;

      >.new-notice{
        min-width:520px;
        height: 194px;
        margin-right: 4px;
        flex-grow:1;
        &:nth-child(odd){
          >ul{

            >li{
              &:nth-child(even){
                background-color: rgb(242, 234, 218);
              }
            }

          }
        }
      }
      /* *************最新学生管理 *******************/
      >.new-students-management{
        min-width:520px;
        height: 194px;
        flex-grow:1;
        &:nth-child(even){
          >ul{

            >li{
              &:nth-child(odd){
                background-color: rgb(242, 234, 218)
              }
            }

          }
        }
      }
      /* *************最新公开课 *******************/
      >.new-public-class{
        min-width:520px;
        height: 298px;
        flex-grow:1;
        margin-top:6px;
        margin-right:4px;

        .speaker{
          float:right;
          display: inline-block;
          width:60px;
          border-left:2px solid #d0c7aa;
          border-right:2px solid #d0c7aa;
          height:26px;
        }
        .pub-ultitle-time{
          float:right;
          display: inline-block;
          min-width:117px;
        }
        .pub-more{
          margin-left:4px;
        }
        .pub-time{
          float:right;
          min-width:117px;
        }
        .pub-announcer{
          border-right:2px solid #d0c7aa;
            float:right;
            width:60px;
            height:26px;
            border-left: 2px solid #d0c7aa;
            color: #4a4949;
        }
        span{

          text-align: center;
          >a{
          color: #4a4949;
          &:hover{
            color: #644635;
            text-decoration: underline;
          }
        }
        }

        &:nth-child(odd){
          >ul{
            .pub-ultitle{
                padding-left: 10px;
                font-weight: bold;
                color: #644635;
                background: url('../assets/images/table_tittle.jpg') repeat-x;
            }

            >li{
              &:nth-child(even){
                background-color: rgb(242, 234, 218)
              }
            }

          }
        }
      }
      /* *************信息修改纪录 *******************/
      >.Modifyinfo{
        min-width:520px;
        height: 298px;
        flex-grow:1;
        margin-top:6px;
        &:nth-child(even){
            >ul{

              >li{
                &:nth-child(odd){
                  background-color: rgb(242, 234, 218)
                }
              }

            }
        }

        ul{
          .mod-ultitle{
           padding-left: 10px;
           font-weight: bold;
           color: #644635;
           background: url('../assets/images/table_tittle.jpg') repeat-x;
           }

        >li{
          display: flex;
          text-align: center;
          span{
            display: inline-block;
          }

        .mod-ultitle-men{
          width:98px;
          border-right:2px solid #d0c7aa;
        }
        .mod-ultitle-time{
          width:98px;
          border-left:2px solid #d0c7aa;
        }
        .mod-ultitle-info{
          flex:1;
        }

        }

        }

      }
      /* *************待办事项区 *******************/
      >.todolist{
        min-width:1050px;
        min-height: 234px;
        background:blue;
        flex-grow:1;
      }
    }
    /* *************右边容器 *******************/
    >.content-right{

      min-width:164px;
      /* *************最新提醒 *******************/
      >.new-remind{
        width:145px;
        height: 116px;
        background: yellow;
      }
      /* *************我的同事 *******************/
      >.colleague{
        width:145px;
        min-height: 610px;
        background: pink;
      }
    }
  }
</style>