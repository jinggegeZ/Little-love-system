<template>
 <div>
    <div><img src="https://wpimg.wallstcn.com/e7d23d71-cf19-4b90-a1cc-f56af8c0903d.png" alt=""></div>
    <div class="progressbar">
        <el-progress v-for="(item,index) in data" :key="index" :percentage="progress" :format="name" :stroke-width='15' status="success"></el-progress>
        
        </div>
 </div>
</template>

<script>
import axios from 'axios'
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
         data:[
            
         ]
     }
   },
   methods: {
    format(percentage) {
        return percentage === 100 ? '满' : `${percentage}%`;
      },
      getData(){
          axios.get('/api/progress').then(res => {
              this.data = res.data.data
              this.progress = data.progress*100
              this.name = data.name 
          }).catch(err => {
              console.log(err);
          })
      }
   },
   mounted() {
       this.getData()
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped>
    .el-progress el-progress--line is-success {
        line-height: 2;
    }
</style>