<template>
  <table class="table">
      <tr class="first">
        <td
          :class="{active:index===firstIndex}"
          v-for="(firstData,index) in menuData"
          :key="index"
          @click="clickFn('firstIndex',index)"
        >{{firstData.alias}}</td>
      </tr>

      <tr class="second">
        <td
          v-for="(sData,index) in menuData[firstIndex].secondData"
          :key="index"
          @click="clickFn('secondIndex',index)"
          :class="{active:index===secondIndex}"
        >{{sData.alias}}</td>
      </tr>

      <tr class="third">
        <td
          v-for="(tData,index) in menuData[firstIndex].secondData[secondIndex].thirdData"
          :key="index"
          @click="clickFn('thirdIndex',index) "
          :class="{active:index===thirdIndex}"
        >{{tData.alias}}</td>
      </tr>

      <tr class="fourth">
        <td
          v-for="(fData,index) in menuData[firstIndex].secondData[secondIndex].thirdData[thirdIndex].fourthData"
          :key="index"
          @click="clickFn('fourthIndex',index)"
          :class="{active:index===fourthIndex}"
        >{{fData.alias}}</td>
    </tr>
  </table>
</template>

<script>
import {  ref} from "vue";
export default {
  name: "LinkageTable",
  props: ["menuData"],
  emits: ["clickFn"],
  setup() {
     const firstIndex = ref(0);
    const secondIndex = ref(0);
    const thirdIndex = ref(0);
    const fourthIndex = ref(0);
    function clickFn(currentIndex, index) {
      eval(currentIndex).value = index;
    }
    return {
       firstIndex,
      secondIndex,
      thirdIndex,
      fourthIndex,
      clickFn,
    };
  },
};
</script>

<style scoped>
</style>
