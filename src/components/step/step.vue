<template>
  <div class="step-box">
    <step-item v-for="item in items" v-bind:item="item" :key="item.id"></step-item>
  </div>

</template>

<script>
  import StepItem from "./step-item"

  export default {
    name: "step",
    data() {
      return {
        items: [
          {id:1,title: "开业审核", status: 1,showLine:false},
          {id:2,title: "核准开业", status: 1,showLine:true},
          {id:3,title: "开业并网", status: 0,showLine:true},
        ]
      }
    },
    components: {StepItem}
  }
</script>

<style scoped lang="less">
.step-box{
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
}
</style>
