<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    height="234"
  >
    <el-table-column
      fixed
      prop="jobs"
      label="招聘岗位"
      width="234">
    </el-table-column>
    <el-table-column
      prop="corp"
      label="公司"
      width="234">
    </el-table-column>
    <el-table-column
      prop="location"
      label="位置"
      width="234">
    </el-table-column>
    <el-table-column
      prop="salary"
      label="薪酬"
      width="234">
    </el-table-column>
    <el-table-column
      prop="time"
      label="发布时间"
      width="234">
    </el-table-column>
    <el-table-column
      prop="order"
      label="岗位要求"
      width="234">
    </el-table-column>
    <el-table-column
      prop="introduction"
      label="岗位描述"
      width="225">
    </el-table-column>
  </el-table>
</template>

<script>
import {fetchData} from "@/api";

export default {
name: "#app",
    data() {
      return {
        query:{
          url:'',

        },
        jobs:[],

      }
    },
  created() {
  this.getjob();
  },
  methods:{
   getjob:function(){
      this.query.url="http://localhost:8000/spider/getJobList"
     fetchData(this.query).then(res=>{
       this.jobs=res.job
     })

    }
  }

}





</script>

<style scoped>

</style>