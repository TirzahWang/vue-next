<template>
  <div class="wrap">
    <div class="navTaxt">
      <div
        v-for="(item,index) in navText"
        :key="index"
      >
        {{item}}
        <i></i>
      </div>
    </div>
      <linkage-table :menuData="menuData" />
  </div>
</template>

<script>
import { reactive } from "vue";
import LinkageTable from './components/LinkageTable';
export default {
  components:{LinkageTable},
  setup() {
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
      ],
      navText: ["数据概览", "历史任务", "创建任务"],
      
    });
   
    
    return {
      menuData: state.menuData,
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