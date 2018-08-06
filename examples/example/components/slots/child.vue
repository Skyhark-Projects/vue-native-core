<template>
  <view>
    <slot name="bottom"></slot>
    <slot name="middle"></slot>
    <slot name="top"></slot>
    <slot></slot> 
  </view>
</template>

<script>
export default {
  props: {
    name: String
  }
};
</script>