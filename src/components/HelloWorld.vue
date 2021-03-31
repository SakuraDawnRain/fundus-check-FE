<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
	<el-row>
		<el-col :span="6">
			<el-menu :default-active="1" class="el-menu-vertical-demo" @select="handleSelect">
				<el-menu-item index="1">快速预测</el-menu-item>
				<el-menu-item index="2">批量预测</el-menu-item>
				<el-menu-item index="3">专家模式</el-menu-item>
			</el-menu>
		</el-col>
		<el-col :span="6">
			<p>图片上传：</p>
			<el-upload
			class="avatar-uploader"
			action="https://jsonplaceholder.typicode.com/posts/"
			:show-file-list="false"
			>
			<img v-if="imageUrl" :src="imageUrl" class="avatar" width="200">
			<i v-else class="el-icon-plus avatar-uploader-icon"></i>
			</el-upload>
			<p></p>
			<el-button type="primary">提交</el-button>
		</el-col>
		<el-col :span="6">
			<p>预测结果：Cataract</p>
			<p>可能性：0.938</p>
		</el-col>
	</el-row>
	
	
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
        return {
          fits: ['fill', 'contain', 'cover', 'none', 'scale-down'],
          imageUrl: require("../assets/cataract_001.png")
        }
      }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
