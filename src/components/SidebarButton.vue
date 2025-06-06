<script setup>
const props = defineProps({
  isActive: {
    type: Boolean,
    default: false
  },
  hlink: {
    type: String,
    default: ''
  }
});

const onclick = () => {
  console.log(props.hlink);
}

</script>

<template>
  <div class = "highlight button" v-on:click="onclick">
    <div v-if="isActive" class ="active bar">
    </div>
    <div style="align-content: center; text-align: center;" class = "sbbutton" :class="{active:isActive}">
      <slot v-if="isActive" name = "icon_active">empty</slot>
      <slot v-else name="icon_default">n-empty</slot>
      <br>
      <slot name = "title">name</slot>
    </div>
  </div>
</template>

<style scoped>
.highlight.button{
  width: 100%;
  height: 64px;
  padding-top: 10px;
  color: #5B5B5B;
  font-size: 16px;
  cursor: pointer;
}
.active.bar{
  width: 5px;
  height: inherit;
  background-color: #FF9335;
  position: absolute;
  left: 0;
}
.sbbutton.active{
  color:#FF9335;
}
#alttext{
  text-anchor: middle;
  text-align: center;
}
</style>