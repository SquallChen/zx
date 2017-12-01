<template>
  <div id="Content">
    <div class="content-left">
      <div class="new-notice">
        <ul>
          <li class="ultitle"><span>最新学校通知</span><span><a href="#" class="more">更多>></a></span></li>
        <!--   <li><span><a href="#">关于2016学年补交教师存档材料的通知</a></span>
          <span class="notice-time">2017-11-28</span>
          <span class="announcer">李流柳</span></li>
          <li><span><a href="#">关于2016学年补交教师存档材料的通知</a></span>
          <span class="notice-time">2017-11-28</span>
          <span class="announcer">李流柳</span></li> -->
          <li  v-for = "(ntcdata,index) in noticedata " v-if="index < 6" :key="ntcdata.index"><span><a href="#">{{ntcdata.notice_title}}</a></span>
          <span class="notice-time">{{ntcdata.release_time}}</span>
          <span class="announcer">{{ntcdata.announcer}}</span></li>
        </ul>
      </div>
      <div class="new-students-management"></div>
      <div class="new-public-class"></div>
      <div class="Modifyinfo"></div>
      <div class="todolist"></div>
    </div>
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
    }
  },
  mounted: function() {
    this.getJsonInfo()
},
methods: {
    getJsonInfo: function() {
        this.$http.get('notice.json').then(function(response){
            console.log(response.data.data)
            var tempdata = response.data.data
            this.noticedata = tempdata
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

    >li{
      height:26px;
      padding-left:14px;
      padding-top:1px;

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

    >.content-left{
      display: flex;
      flex-wrap: wrap;
      flex-grow:1;

      >.new-notice{
        min-width:520px;
        height: 194px;
        flex-grow:1;
        &:nth-child(odd){
        >ul{
          border-left: 3px solid #d0c7aa;
          border-right: 3px solid #d0c7aa;
          >li{
            &:nth-child(even){
              background-color: rgb(242, 234, 218)
          }
          }

        }
        }
      }
      >.new-students-management{
        min-width:520px;
        height: 194px;
        background: blue;
        flex-grow:1;
      }
      >.new-public-class{
        min-width:520px;
        height: 298px;
        background: black;
        flex-grow:1;
      }
      >.Modifyinfo{
        min-width:520px;
        height: 298px;
        background: orange;
        flex-grow:1;
      }
      >.todolist{
        min-width:1050px;
        min-height: 234px;
        background:blue;
        flex-grow:1;
      }
    }
    >.content-right{

      min-width:164px;
      >.new-remind{
        width:145px;
        height: 116px;
        background: yellow;
      }
      >.colleague{
        width:145px;
        min-height: 610px;
        background: pink;
      }
    }
  }
</style>