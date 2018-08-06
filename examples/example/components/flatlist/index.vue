<template>
  <view class="container">
    <flat-list
      :style="{ overflow: 'hidden'}"
      :data="[{key: 'a',value:{
        iconName:'plane',
        text:'Airplane Mode',
        switchValue:false,
        isSwitchAvail:true,

      }},{key: 'b',value:{
        iconName:'wifi',
        text:'Wi-Fi',
        rightName:'GeekyAnts',
        rightIcon:'arrow-forward',
        isSwitchAvail:false,
        
      }},{key: 'c',value:{
        iconName:'bluetooth',
        text:'Bluetooth',
        rightName:'On',
        rightIcon:'arrow-forward',
        isSwitchAvail:false,
        
      }}]" >
  <view render-prop-fn="renderItem"  >
    <nb-list-item icon>
        <nb-left>
          <nb-button :style="{ backgroundColor: '#FF9501' }">
            <nb-icon active :name="args.item.value.iconName" />
          </nb-button>
        </nb-left>
        <nb-body>
          <nb-text>{{args.item.value.text}}</nb-Text>
        </nb-body>
        <nb-right v-if="args.item.value.isSwitchAvail">
          <nb-switch :value="args.item.value.switchValue" />
      </nb-right>
      <nb-right v-else>
        <nb-text>{{args.item.value.rightName}}</nb-text>
          <nb-icon active :name="args.item.value.rightIcon" />
      </nb-right>
    </nb-list-item>    
  </view>
  
</flat-list>

       
  </view>
</template>

<script>
import { ListView } from "react-native";
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";
Vue.use(VueNativeBase);
export default {};
</script>

 
<style>
.container {
  background-color: white;
  padding-top: 30;
  /* align-items: center; */
  /* justify-content: center; */
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>

