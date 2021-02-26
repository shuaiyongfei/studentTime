<template>
   <div class="el-container">
        <el-row :gutter="10">
            <el-col :span="4">
                <div class="">
                    <el-input
                        placeholder="请输入姓名"
                        size="small">
                    </el-input>
                </div>
            </el-col>
            <el-col :span="17">
                <div class="">
                    <el-date-picker
                        type="daterange"
                        align="right"
                        unlink-panels
                        range-separator="~"
                        start-placeholder="开始日期"
                        end-placeholder="结束日期"
                        format="yyyy-MM-dd"
                        value-format="yyyy-MM-dd"
                        size="small"
                        >
                    </el-date-picker>
                </div>
            </el-col>
            <el-col :span="3">
                <div class="">
                    <el-button
                        type="primary"
                        icon="el-icon-search"
                        size="small"
                        @click="search">
                        搜索
                    </el-button>
                </div>
            </el-col>
        </el-row>
   </div>
</template>

<script>
export default {
  data() {
    return {
     date:"adsa",
     searchname:"xioa",
    }
  },
  props:{
    modelname:String 
  },
  methods: {
    search(){
      let path=null;
      if(this.modelname==='团队出勤情况')
      {
        path='/personal_attendance'
      }
      else{
        path='/personal_vocation'
      }
      // let searchname=this.searchname
      // let date=this.date
      this.$router.push({
                        path,
                        query:{ searchname:'小明',date:null}
                        })
    }
  }
}
</script>

<style>

</style>