<template>
 <div>
    <div class="pbbox">
      <div class="pbhead">
          <el-button type="danger">查看</el-button>
          <el-button type="primary">发布</el-button>
      </div>
    </div>

    <div>
    <el-form :model="numberValidateForm" ref="numberValidateForm" label-width="100px" class="demo-ruleForm">
    <el-form-item label="文章标题" prop="age" :rules="[{ required: true,}, { type: 'text',}]">
      <el-input type="age" v-model.number="numberValidateForm.age" autocomplete="off"></el-input>
    </el-form-item>
      <el-form-item label="文章摘要" prop="age" :rules="[{ required: true,}, { type: 'text',}]">
      <el-input type="age" v-model.number="numberValidateForm.age" autocomplete="off"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="submitForm('numberValidateForm')">提交</el-button>
      <el-button @click="resetForm('numberValidateForm')">重置</el-button>
    </el-form-item>
    </el-form>
    </div>

      <div>
          <mavon-editor v-model="value"/>
      </div>
 </div>
</template>

<script>

 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
         value:'',
         numberValidateForm: {
          age: ''
        },
         
     }
   },
   methods: {
     submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
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

<style scoped lang='scss'>

</style>