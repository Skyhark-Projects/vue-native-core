<template>
   <view class="container">
     <child>
       <text slot="top">Top text</text>
       <text slot="bottom">Bottom text</text>
       <text>Text with no name</text>
      <text slot="middle">Middle text</text>
      </child>
   </view>
  
</template>

<script>
import child from "./child";
import { ListView } from "react-native";
export default {
  data: {
    test: false,
    dataSource: 0
  },
  components: { child }
};
</script>

 
<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
