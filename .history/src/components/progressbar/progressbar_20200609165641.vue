<template>
 <div>
    <div><img src="https://wpimg.wallstcn.com/e7d23d71-cf19-4b90-a1cc-f56af8c0903d.png" alt=""></div>
    <div class="progressbar">
        <el-progress :percentage="50" :stroke-width='15'></el-progress>
        <el-progress :percentage="100" :format="format" :stroke-width='15'></el-progress>
        <el-progress :percentage="100" status="success" :stroke-width='15'></el-progress>
        <el-progress :percentage="100" status="warning" :stroke-width='15'></el-progress>
        <el-progress :percentage="50" status="exception" :stroke-width='15'></el-progress>
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

     }
   },
   methods: {
    format(percentage) {
        return percentage === 100 ? '满' : `${percentage}%`;
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

</style>