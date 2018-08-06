<template>
 
<!-- <custom-flat-list></custom-flat-list> -->
<slot-sample></slot-sample>
</template>

<script>
import customFlatList from "./components/flatlist/index";
import slotSample from "./components/slots/parent";
export default {
  components: { customFlatList, slotSample }
};
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
