<template>
 <div>
    <div class="box">
        <div class="box-head">
            <div><input type="text" placeholder="请输入商品名" class="box-ipt"></div>
        </div>
        <div class="box-nav">
            <el-table :data="tableData" style="width: 100%">
                <el-table-column label="名称" width="250" prop="names">
                    <template slot-scope="scope">
                        <span style="margin-left: 10px">{{ scope.row.date }}</span>
                    </template>
                </el-table-column>
                <el-table-column label="商品编号" width="250" prop="goodsum">
                    <template slot-scope="scope">
                        <span style="margin-left: 10px">{{ scope.row.date }}</span>
                    </template>
                </el-table-column>
                <el-table-column label="原价" width="250" prop="oldprice">
                    <template slot-scope="scope">
                        <span style="margin-left: 10px">{{ scope.row.date }}</span>
                    </template>
                </el-table-column>
                <el-table-column label="现价" width="250" prop="presentprice">
                    <template slot-scope="scope">
                    <el-popover trigger="hover" placement="top">
                    <p>姓名: {{ scope.row.name }}</p>
                    <p>住址: {{ scope.row.address }}</p>
                <div slot="reference" class="name-wrapper">
                    <el-tag size="medium">{{ scope.row.name }}</el-tag>
                </div>
                    </el-popover>
                    </template>
                </el-table-column>
                <el-table-column label="操作">
                    <template slot-scope="scope">
                        <el-button size="mini" @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
                        <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">删除</el-button>
                    </template>
                </el-table-column>
            </el-table>
        </div>
        <div class="box-foot">
            <div><el-button type="primary">导出xls</el-button></div>
            <div><el-button type="danger">导出csv</el-button></div>
        </div>
    </div>
 </div>
</template>

<script>
import axios from 'axios'
 export default {
   name: 'deriveExcel',
   props: {
   },
   components: {

   },
   data () {
     return {
         tableData: [{
          name:'',
          goodsum:'',
          oldprice:'',
          presentprice:'',
        },]
     }
   },
   methods: {
        handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      },
      getData(){
          axios.get('/api/')
      }
   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped>
    .box {
        width: 100%;
        border: 1px solid #dddddd;
        box-shadow: 0 1px 2px 0 #ddd;
    }
    .box-head {
        width: 100px;
        height: 10%;
        margin-bottom: 15px;
    }
    .box-nav {
        width: 100%;
        height: 70%;
        margin-bottom: 15px;
    }
    .box-foot {
        width: 200px;
        height: 10%;
        display: flex;
        justify-content: space-around;
        align-items: center;
    }
    .box-ipt {
        height: 30px;
        width: 200px;
    }
</style>