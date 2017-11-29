<template>
  <div id="Content">
    <div class="content-left">
      <div class="new-notice"></div>
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
  name: 'Content'
}
</script>

<style lang="scss">
  #Content{
    justify-content: space-between;
    background: white;
    flex-grow: 1;
    margin-top:15px;
    display: flex;


    >.content-left{
      display: flex;
      flex-wrap: wrap;
      flex-grow:1;

      >.new-notice{
        min-width:520px;
        height: 194px;
        background: green;
        flex-grow:1;

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