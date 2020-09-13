<template>
  <div class="wrap">
    <div class="navTaxt">
      <div
        v-for="(item,index) in navText"
        :key="index"
        :class="{currentNav:index==navIndex}"
        @click="clickFn('navIndex',index)"
      >
        {{item}}
        <i></i>
      </div>
    </div>
    <table class="table" cellspacing="0" cellpadding="0" v-show="navIndex==0">
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
  </div>
</template>

<script>
import { reactive, onMounted, ref, watchEffect } from "vue";

export default {
  setup() {
    function clickFn(currentIndex, index) {
      eval(currentIndex).value = index;
    }
    const navIndex = ref(0);
    const firstIndex = ref(0);
    const secondIndex = ref(0);
    const thirdIndex = ref(0);
    const fourthIndex = ref(0);
    const state = reactive({
      menuData: [
        {
          id: "01",
          alias: "一级",
          secondData: [
            {
              id: "10",
              alias: "1-0",
              thirdData: [
                {
                  id: "100",
                  alias: "1-0-0",
                  fourthData: [
                    { id: "1000", alias: "1-0-0-0" },
                    { id: "1001", alias: "1-0-0-1" },
                    { id: "1002", alias: "1-0-0-2" },
                    { id: "1003", alias: "1-0-0-3" },
                  ],
                },
                {
                  id: "101",
                  alias: "1-0-1",
                  fourthData: [
                    { id: "1010", alias: "1-0-1-0" },
                    { id: "1011", alias: "1-0-1-1" },
                    { id: "1012", alias: "1-0-1-2" },
                    { id: "1013", alias: "1-0-1-3" },
                  ],
                },
                {
                  id: "102",
                  alias: "1-0-2",
                  fourthData: [
                    { id: "1020", alias: "1-0-2-0" },
                    { id: "1021", alias: "1-0-2-1" },
                    { id: "1022", alias: "1-0-2-2" },
                    { id: "1023", alias: "1-0-2-3" },
                  ],
                },
                {
                  id: "103",
                  alias: "1-0-3",
                  fourthData: [
                    { id: "1030", alias: "1-0-3-0" },
                    { id: "1031", alias: "1-0-3-1" },
                    { id: "1032", alias: "1-0-3-2" },
                    { id: "1033", alias: "1-0-3-3" },
                  ],
                },
              ],
            },
            {
              id: "11",
              alias: "1-1",
              thirdData: [
                {
                  id: "110",
                  alias: "1-1-0",
                  fourthData: [
                    { id: "1100", alias: "1-1-0-0" },
                    { id: "1101", alias: "1-1-0-1" },
                    { id: "1102", alias: "1-1-0-2" },
                    { id: "1103", alias: "1-1-0-3" },
                  ],
                },
                {
                  id: "111",
                  alias: "1-1-1",
                  fourthData: [
                    { id: "1110", alias: "1-1-1-0" },
                    { id: "1111", alias: "1-1-1-1" },
                    { id: "1112", alias: "1-1-1-2" },
                    { id: "1113", alias: "1-1-1-3" },
                  ],
                },
                {
                  id: "112",
                  alias: "1-1-2",
                  fourthData: [
                    { id: "1120", alias: "1-1-2-0" },
                    { id: "1121", alias: "1-1-2-1" },
                    { id: "1122", alias: "1-1-2-2" },
                    { id: "1123", alias: "1-1-2-3" },
                  ],
                },
                {
                  id: "113",
                  alias: "1-1-3",
                  fourthData: [
                    { id: "1130", alias: "1-1-3-0" },
                    { id: "1131", alias: "1-1-3-1" },
                    { id: "1132", alias: "1-1-3-2" },
                    { id: "1133", alias: "1-1-3-3" },
                  ],
                },
              ],
            },
            {
              id: "12",
              alias: "1-2",
              thirdData: [
                {
                  id: "120",
                  alias: "1-2-0",
                  fourthData: [
                    { id: "1200", alias: "1-2-0-0" },
                    { id: "1201", alias: "1-2-0-1" },
                    { id: "1202", alias: "1-2-0-2" },
                    { id: "1203", alias: "1-2-0-3" },
                  ],
                },
                {
                  id: "121",
                  alias: "1-2-1",
                  fourthData: [
                    { id: "1210", alias: "1-2-1-0" },
                    { id: "1211", alias: "1-2-1-1" },
                    { id: "1212", alias: "1-2-1-2" },
                    { id: "1213", alias: "1-2-1-3" },
                  ],
                },
                {
                  id: "122",
                  alias: "1-2-2",
                  fourthData: [
                    { id: "1220", alias: "1-2-2-0" },
                    { id: "1221", alias: "1-2-2-1" },
                    { id: "1222", alias: "1-2-2-2" },
                    { id: "1223", alias: "1-2-2-3" },
                  ],
                },
                {
                  id: "123",
                  alias: "1-2-3",
                  fourthData: [
                    { id: "1230", alias: "1-2-3-0" },
                    { id: "1231", alias: "1-2-3-1" },
                    { id: "1232", alias: "1-2-3-2" },
                    { id: "1233", alias: "1-2-3-3" },
                  ],
                },
              ],
            },
            {
              id: "13",
              alias: "1-3",
              thirdData: [
                {
                  id: "130",
                  alias: "1-3-0",
                  fourthData: [
                    { id: "1300", alias: "1-3-0-0" },
                    { id: "1301", alias: "1-3-0-1" },
                    { id: "1302", alias: "1-3-0-2" },
                    { id: "1303", alias: "1-3-0-3" },
                  ],
                },
                {
                  id: "131",
                  alias: "1-3-1",
                  fourthData: [
                    { id: "1310", alias: "1-3-1-0" },
                    { id: "1311", alias: "1-3-1-1" },
                    { id: "1312", alias: "1-3-1-2" },
                    { id: "1313", alias: "1-3-1-3" },
                  ],
                },
                {
                  id: "132",
                  alias: "1-3-2",
                  fourthData: [
                    { id: "1320", alias: "1-3-2-0" },
                    { id: "1321", alias: "1-3-2-1" },
                    { id: "1322", alias: "1-3-2-2" },
                    { id: "1323", alias: "1-3-2-3" },
                  ],
                },
                {
                  id: "133",
                  alias: "1-3-3",
                  fourthData: [
                    { id: "1330", alias: "1-3-3-0" },
                    { id: "1331", alias: "1-3-3-1" },
                    { id: "1332", alias: "1-3-3-2" },
                    { id: "1333", alias: "1-3-3-3" },
                  ],
                },
              ],
            },
          ],
        },
        {
          id: "02",
          alias: "二级",
          secondData: [
            {
              id: "20",
              alias: "2-0",
              thirdData: [
                {
                  id: "200",
                  alias: "2-0-0",
                  fourthData: [
                    { id: "2000", alias: "2-0-0-0" },
                    { id: "2001", alias: "2-0-0-1" },
                    { id: "2002", alias: "2-0-0-2" },
                    { id: "2003", alias: "2-0-0-3" },
                  ],
                },
                {
                  id: "201",
                  alias: "2-0-1",
                  fourthData: [
                    { id: "2010", alias: "2-0-1-0" },
                    { id: "2011", alias: "2-0-1-1" },
                    { id: "2012", alias: "2-0-1-2" },
                    { id: "2013", alias: "2-0-1-3" },
                  ],
                },
                {
                  id: "202",
                  alias: "2-0-2",
                  fourthData: [
                    { id: "2020", alias: "2-0-2-0" },
                    { id: "2021", alias: "2-0-2-1" },
                    { id: "2022", alias: "2-0-2-2" },
                    { id: "2023", alias: "2-0-2-3" },
                  ],
                },
                {
                  id: "203",
                  alias: "2-0-3",
                  fourthData: [
                    { id: "2030", alias: "2-0-3-0" },
                    { id: "2031", alias: "2-0-3-1" },
                    { id: "2032", alias: "2-0-3-2" },
                    { id: "2033", alias: "2-0-3-3" },
                  ],
                },
              ],
            },
            {
              id: "21",
              alias: "2-1",
              thirdData: [
                {
                  id: "210",
                  alias: "2-1-0",
                  fourthData: [
                    { id: "2100", alias: "2-1-0-0" },
                    { id: "2101", alias: "2-1-0-1" },
                    { id: "2102", alias: "2-1-0-2" },
                    { id: "2103", alias: "2-1-0-3" },
                  ],
                },
                {
                  id: "211",
                  alias: "2-1-1",
                  fourthData: [
                    { id: "2110", alias: "2-1-1-0" },
                    { id: "2111", alias: "2-1-1-1" },
                    { id: "2112", alias: "2-1-1-2" },
                    { id: "2113", alias: "2-1-1-3" },
                  ],
                },
                {
                  id: "212",
                  alias: "2-1-2",
                  fourthData: [
                    { id: "2120", alias: "2-1-2-0" },
                    { id: "2121", alias: "2-1-2-1" },
                    { id: "2122", alias: "2-1-2-2" },
                    { id: "2123", alias: "2-1-2-3" },
                  ],
                },
                {
                  id: "213",
                  alias: "2-1-3",
                  fourthData: [
                    { id: "2130", alias: "2-1-3-0" },
                    { id: "2131", alias: "2-1-3-1" },
                    { id: "2132", alias: "2-1-3-2" },
                    { id: "2133", alias: "2-1-3-3" },
                  ],
                },
              ],
            },
            {
              id: "22",
              alias: "2-2",
              thirdData: [
                {
                  id: "220",
                  alias: "2-2-0",
                  fourthData: [
                    { id: "2200", alias: "2-2-0-0" },
                    { id: "2201", alias: "2-2-0-1" },
                    { id: "2202", alias: "2-2-0-2" },
                    { id: "2203", alias: "2-2-0-3" },
                  ],
                },
                {
                  id: "221",
                  alias: "2-2-1",
                  fourthData: [
                    { id: "2210", alias: "2-2-1-0" },
                    { id: "2211", alias: "2-2-1-1" },
                    { id: "2212", alias: "2-2-1-2" },
                    { id: "2213", alias: "2-2-1-3" },
                  ],
                },
                {
                  id: "222",
                  alias: "2-2-2",
                  fourthData: [
                    { id: "2220", alias: "2-2-2-0" },
                    { id: "2221", alias: "2-2-2-1" },
                    { id: "2222", alias: "2-2-2-2" },
                    { id: "2223", alias: "2-2-2-3" },
                  ],
                },
                {
                  id: "223",
                  alias: "2-2-3",
                  fourthData: [
                    { id: "2230", alias: "2-2-3-0" },
                    { id: "2231", alias: "2-2-3-1" },
                    { id: "2232", alias: "2-2-3-2" },
                    { id: "2233", alias: "2-2-3-3" },
                  ],
                },
              ],
            },
            {
              id: "23",
              alias: "2-3",
              thirdData: [
                {
                  id: "230",
                  alias: "2-3-0",
                  fourthData: [
                    { id: "2300", alias: "2-3-0-0" },
                    { id: "2301", alias: "2-3-0-1" },
                    { id: "2302", alias: "2-3-0-2" },
                    { id: "2303", alias: "2-3-0-3" },
                  ],
                },
                {
                  id: "231",
                  alias: "2-3-1",
                  fourthData: [
                    { id: "2310", alias: "2-3-1-0" },
                    { id: "2311", alias: "2-3-1-1" },
                    { id: "2312", alias: "2-3-1-2" },
                    { id: "2313", alias: "2-3-1-3" },
                  ],
                },
                {
                  id: "232",
                  alias: "2-3-2",
                  fourthData: [
                    { id: "2320", alias: "2-3-2-0" },
                    { id: "2321", alias: "2-3-2-1" },
                    { id: "2322", alias: "2-3-2-2" },
                    { id: "2323", alias: "2-3-2-3" },
                  ],
                },
                {
                  id: "233",
                  alias: "2-3-3",
                  fourthData: [
                    { id: "2330", alias: "2-3-3-0" },
                    { id: "2331", alias: "2-3-3-1" },
                    { id: "2332", alias: "2-3-3-2" },
                    { id: "2333", alias: "2-3-3-3" },
                  ],
                },
              ],
            },
          ],
        },
        {
          id: "03",
          alias: "三级",
          secondData: [
            {
              id: "30",
              alias: "3-0",
              thirdData: [
                {
                  id: "300",
                  alias: "3-0-0",
                  fourthData: [
                    { id: "3000", alias: "3-0-0-0" },
                    { id: "3001", alias: "3-0-0-1" },
                    { id: "3002", alias: "3-0-0-2" },
                    { id: "3003", alias: "3-0-0-3" },
                  ],
                },
                {
                  id: "301",
                  alias: "3-0-1",
                  fourthData: [
                    { id: "3010", alias: "3-0-1-0" },
                    { id: "3011", alias: "3-0-1-1" },
                    { id: "3012", alias: "3-0-1-2" },
                    { id: "3013", alias: "3-0-1-3" },
                  ],
                },
                {
                  id: "302",
                  alias: "3-0-2",
                  fourthData: [
                    { id: "3020", alias: "3-0-2-0" },
                    { id: "3021", alias: "3-0-2-1" },
                    { id: "3022", alias: "3-0-2-2" },
                    { id: "3023", alias: "3-0-2-3" },
                  ],
                },
                {
                  id: "303",
                  alias: "3-0-3",
                  fourthData: [
                    { id: "3030", alias: "3-0-3-0" },
                    { id: "3031", alias: "3-0-3-1" },
                    { id: "3032", alias: "3-0-3-2" },
                    { id: "3033", alias: "3-0-3-3" },
                  ],
                },
              ],
            },
            {
              id: "31",
              alias: "3-1",
              thirdData: [
                {
                  id: "310",
                  alias: "3-1-0",
                  fourthData: [
                    { id: "3100", alias: "3-1-0-0" },
                    { id: "3101", alias: "3-1-0-1" },
                    { id: "3102", alias: "3-1-0-2" },
                    { id: "3103", alias: "3-1-0-3" },
                  ],
                },
                {
                  id: "311",
                  alias: "3-1-1",
                  fourthData: [
                    { id: "3110", alias: "3-1-1-0" },
                    { id: "3111", alias: "3-1-1-1" },
                    { id: "3112", alias: "3-1-1-2" },
                    { id: "3113", alias: "3-1-1-3" },
                  ],
                },
                {
                  id: "312",
                  alias: "3-1-2",
                  fourthData: [
                    { id: "3120", alias: "3-1-2-0" },
                    { id: "3121", alias: "3-1-2-1" },
                    { id: "3122", alias: "3-1-2-2" },
                    { id: "3123", alias: "3-1-2-3" },
                  ],
                },
                {
                  id: "313",
                  alias: "3-1-3",
                  fourthData: [
                    { id: "3130", alias: "3-1-3-0" },
                    { id: "3131", alias: "3-1-3-1" },
                    { id: "3132", alias: "3-1-3-2" },
                    { id: "3133", alias: "3-1-3-3" },
                  ],
                },
              ],
            },
            {
              id: "32",
              alias: "3-2",
              thirdData: [
                {
                  id: "320",
                  alias: "3-2-0",
                  fourthData: [
                    { id: "3200", alias: "3-2-0-0" },
                    { id: "3201", alias: "3-2-0-1" },
                    { id: "3202", alias: "3-2-0-2" },
                    { id: "3203", alias: "3-2-0-3" },
                  ],
                },
                {
                  id: "321",
                  alias: "3-2-1",
                  fourthData: [
                    { id: "3210", alias: "3-2-1-0" },
                    { id: "3211", alias: "3-2-1-1" },
                    { id: "3212", alias: "3-2-1-2" },
                    { id: "3213", alias: "3-2-1-3" },
                  ],
                },
                {
                  id: "322",
                  alias: "3-2-2",
                  fourthData: [
                    { id: "3220", alias: "3-2-2-0" },
                    { id: "3221", alias: "3-2-2-1" },
                    { id: "3222", alias: "3-2-2-2" },
                    { id: "3223", alias: "3-2-2-3" },
                  ],
                },
                {
                  id: "323",
                  alias: "3-2-3",
                  fourthData: [
                    { id: "3230", alias: "3-2-3-0" },
                    { id: "3231", alias: "3-2-3-1" },
                    { id: "3232", alias: "3-2-3-2" },
                    { id: "3233", alias: "3-2-3-3" },
                  ],
                },
              ],
            },
            {
              id: "33",
              alias: "3-3",
              thirdData: [
                {
                  id: "330",
                  alias: "3-3-0",
                  fourthData: [
                    { id: "3300", alias: "3-3-0-0" },
                    { id: "3301", alias: "3-3-0-1" },
                    { id: "3302", alias: "3-3-0-2" },
                    { id: "3303", alias: "3-3-0-3" },
                  ],
                },
                {
                  id: "331",
                  alias: "3-3-1",
                  fourthData: [
                    { id: "3310", alias: "3-3-1-0" },
                    { id: "3311", alias: "3-3-1-1" },
                    { id: "3312", alias: "3-3-1-2" },
                    { id: "3313", alias: "3-3-1-3" },
                  ],
                },
                {
                  id: "332",
                  alias: "3-3-2",
                  fourthData: [
                    { id: "3320", alias: "3-3-2-0" },
                    { id: "3321", alias: "3-3-2-1" },
                    { id: "3322", alias: "3-3-2-2" },
                    { id: "3323", alias: "3-3-2-3" },
                  ],
                },
                {
                  id: "333",
                  alias: "3-3-3",
                  fourthData: [
                    { id: "3330", alias: "3-3-3-0" },
                    { id: "3331", alias: "3-3-3-1" },
                    { id: "3332", alias: "3-3-3-2" },
                    { id: "3333", alias: "3-3-3-3" },
                  ],
                },
              ],
            },
          ],
        },
        {
          id: "04",
          alias: "四级",
          secondData: [
            {
              id: "40",
              alias: "4-0",
              thirdData: [
                {
                  id: "400",
                  alias: "4-0-0",
                  fourthData: [
                    { id: "4000", alias: "4-0-0-0" },
                    { id: "4001", alias: "4-0-0-1" },
                    { id: "4002", alias: "4-0-0-2" },
                    { id: "4003", alias: "4-0-0-3" },
                  ],
                },
                {
                  id: "401",
                  alias: "4-0-1",
                  fourthData: [
                    { id: "4010", alias: "4-0-1-0" },
                    { id: "4011", alias: "4-0-1-1" },
                    { id: "4012", alias: "4-0-1-2" },
                    { id: "4013", alias: "4-0-1-3" },
                  ],
                },
                {
                  id: "402",
                  alias: "4-0-2",
                  fourthData: [
                    { id: "4020", alias: "4-0-2-0" },
                    { id: "4021", alias: "4-0-2-1" },
                    { id: "4022", alias: "4-0-2-2" },
                    { id: "4023", alias: "4-0-2-3" },
                  ],
                },
                {
                  id: "403",
                  alias: "4-0-3",
                  fourthData: [
                    { id: "4030", alias: "4-0-3-0" },
                    { id: "4031", alias: "4-0-3-1" },
                    { id: "4032", alias: "4-0-3-2" },
                    { id: "4033", alias: "4-0-3-3" },
                  ],
                },
              ],
            },
            {
              id: "41",
              alias: "4-1",
              thirdData: [
                {
                  id: "410",
                  alias: "4-1-0",
                  fourthData: [
                    { id: "4100", alias: "4-1-0-0" },
                    { id: "4101", alias: "4-1-0-1" },
                    { id: "4102", alias: "4-1-0-2" },
                    { id: "4103", alias: "4-1-0-3" },
                  ],
                },
                {
                  id: "411",
                  alias: "4-1-1",
                  fourthData: [
                    { id: "4110", alias: "4-1-1-0" },
                    { id: "4111", alias: "4-1-1-1" },
                    { id: "4112", alias: "4-1-1-2" },
                    { id: "4113", alias: "4-1-1-3" },
                  ],
                },
                {
                  id: "412",
                  alias: "4-1-2",
                  fourthData: [
                    { id: "4120", alias: "4-1-2-0" },
                    { id: "4121", alias: "4-1-2-1" },
                    { id: "4122", alias: "4-1-2-2" },
                    { id: "4123", alias: "4-1-2-3" },
                  ],
                },
                {
                  id: "413",
                  alias: "4-1-3",
                  fourthData: [
                    { id: "4130", alias: "4-1-3-0" },
                    { id: "4131", alias: "4-1-3-1" },
                    { id: "4132", alias: "4-1-3-2" },
                    { id: "4133", alias: "4-1-3-3" },
                  ],
                },
              ],
            },
            {
              id: "42",
              alias: "4-2",
              thirdData: [
                {
                  id: "420",
                  alias: "4-2-0",
                  fourthData: [
                    { id: "4200", alias: "4-2-0-0" },
                    { id: "4201", alias: "4-2-0-1" },
                    { id: "4202", alias: "4-2-0-2" },
                    { id: "4203", alias: "4-2-0-3" },
                  ],
                },
                {
                  id: "421",
                  alias: "4-2-1",
                  fourthData: [
                    { id: "4210", alias: "4-2-1-0" },
                    { id: "4211", alias: "4-2-1-1" },
                    { id: "4212", alias: "4-2-1-2" },
                    { id: "4213", alias: "4-2-1-3" },
                  ],
                },
                {
                  id: "422",
                  alias: "4-2-2",
                  fourthData: [
                    { id: "4220", alias: "4-2-2-0" },
                    { id: "4221", alias: "4-2-2-1" },
                    { id: "4222", alias: "4-2-2-2" },
                    { id: "4223", alias: "4-2-2-3" },
                  ],
                },
                {
                  id: "423",
                  alias: "4-2-3",
                  fourthData: [
                    { id: "4230", alias: "4-2-3-0" },
                    { id: "4231", alias: "4-2-3-1" },
                    { id: "4232", alias: "4-2-3-2" },
                    { id: "4233", alias: "4-2-3-3" },
                  ],
                },
              ],
            },
            {
              id: "43",
              alias: "4-3",
              thirdData: [
                {
                  id: "430",
                  alias: "4-3-0",
                  fourthData: [
                    { id: "4300", alias: "4-3-0-0" },
                    { id: "4301", alias: "4-3-0-1" },
                    { id: "4302", alias: "4-3-0-2" },
                    { id: "4303", alias: "4-3-0-3" },
                  ],
                },
                {
                  id: "431",
                  alias: "4-3-1",
                  fourthData: [
                    { id: "4310", alias: "4-3-1-0" },
                    { id: "4311", alias: "4-3-1-1" },
                    { id: "4312", alias: "4-3-1-2" },
                    { id: "4313", alias: "4-3-1-3" },
                  ],
                },
                {
                  id: "432",
                  alias: "4-3-2",
                  fourthData: [
                    { id: "4320", alias: "4-3-2-0" },
                    { id: "4321", alias: "4-3-2-1" },
                    { id: "4322", alias: "4-3-2-2" },
                    { id: "4323", alias: "4-3-2-3" },
                  ],
                },
                {
                  id: "433",
                  alias: "4-3-3",
                  fourthData: [
                    { id: "4330", alias: "4-3-3-0" },
                    { id: "4331", alias: "4-3-3-1" },
                    { id: "4332", alias: "4-3-3-2" },
                    { id: "4333", alias: "4-3-3-3" },
                  ],
                },
              ],
            },
          ],
        },
      ],
      navText: ["数据概览", "历史任务", "创建任务"],
    });
    return {
      navIndex,
      firstIndex,
      secondIndex,
      thirdIndex,
      fourthIndex,
      menuData: state.menuData,
      clickFn,
      navText: state.navText,
    };
  },
};
</script>

<style>
@import url("./assets/css/all.css");
.wrap {
  color: rgb(116, 114, 114);
  font-size: 15px;
  width: 80%;
  margin: 0 auto;
}
.navTaxt {
  display: flex;
}
.navTaxt div {
  margin-bottom: 2px;
  margin: 0 13px;
}
.navTaxt div i {
  display: block;
  width: 35px;
  height: 3px;
  margin-top: 10px;
  margin-left: 9px;
}

.currentNav {
  color: rgb(26, 162, 247);
}
.currentNav i {
  background-color: rgb(26, 162, 247);
}
.table {
  position: relative;
  display: flex;
  justify-content: space-between;
  height: 600px;
  border: 2px solid #ccc;
  overflow: hidden;
  border-collapse: collapse;
}
thead {
  float: left;
}
tr {
  flex: 1;
  border-right: 2px solid rgb(173, 171, 171);
}
tbody tr {
  display: inline-block;
}
th,
td {
  height: 30px;
  line-height: 30px;
  display: block;
  text-align: center;
  border-top: 1px solid rgb(173, 171, 171);
  border-bottom: none;
  color: rgb(90, 90, 90);
}
.active {
  background-color: rgb(214, 210, 210);
}
.fourth td::after {
  position: absolute;
  content: "\f06e";
  font-family: "Font Awesome 5 Free";
  font-size: 13px;
  font-weight: 600;
  right: 15px;
}
</style>