<template>
  <div :class="[!item.showLine?firstItem:'',defaultItem]">
    <div :class="[item.status?finishLine:'',defaultLine]" v-show="item.showLine"></div>
    <div class="icon-title">
      <template v-if="item.status">
        <div class="icon-box">
          <div class="icon-finish"></div>
        </div>
      </template>
      <template v-else>
        <div class="icon-box">
          <div class="icon-wait"></div>
        </div>
      </template>
      <div>{{item.title}}</div>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'step-item',
    data() {
      return {
        defaultLine: 'line',
        finishLine: 'line-finish',
        firstItem: "first-item",
        defaultItem:"step-item"
      }
    },
    props: ['item']
  }
</script>

<style scoped lang="less">
  .step-item {
    position: relative;
    flex: 5;
    .icon-title {
      position: absolute;
      right: 0px;
      text-align: center;
      font-size: 12px;
    }
    .line {
      width: calc(100% - 23px);;
      border-bottom: 1px solid #cfcfcf;
      position: absolute;
      top: 10px;
    }

    .line-finish {
      border-bottom: 1px solid #EC3737;
    }

    .icon-box {
      width: 30px;
      height: 20px;
      position: relative;
      background-color: #ffffff;
    }

    .icon-finish {
      width: 18px;
      height: 18px;
      background-color: #fff;
      border: 6px solid #EC3737;
      box-sizing: border-box;
      border-radius: 50%;
      margin: auto;
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
    }

    .icon-wait {
      width: 12px;
      height: 12px;
      background-color: #fff;
      border: 4px solid #cfcfcf;
      border-radius: 50%;
      box-sizing: border-box;
      margin: auto;
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
    }

  }

  .first-item {
    flex: 1;
  }

</style>
