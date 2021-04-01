<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
	<el-row>
		<el-col :span="6">
			<el-menu :default-active="1" class="el-menu-vertical-demo" @select="handleSelect">
				<el-menu-item index="1">快速预测</el-menu-item>
				<el-menu-item index="2">专家模式</el-menu-item>
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
			<p>模型选择：</p>
			<el-select v-model="value">
				<el-option
				v-for="item in options"
				:key="item.value"
				:label="item.label"
				:value="item.value">
				</el-option>
			</el-select>
			<p></p>
			<el-button type="primary">提交</el-button>
		</el-col>
		<el-col :span="6">
			<p>预测结果*：Cataract</p>
			<p>可能性：0.938</p>
			<p>分级：\</p>
			<p>相关资料：<a href="https://zh.wikipedia.org/zh-tw/%E7%99%BD%E5%86%85%E9%9A%9C">维基百科-白内障</a>
			</p>
			<p></p>
		</el-col>
		<el-col :span="6">
			<p>诊断建议*:</p>
			<p>影像中小血管模糊，建议立即就医。</p>
		</el-col>
	</el-row>
	<p></p>
	<p align="center">*: 在线诊断结果仅供参考，请到正规医院就医并以临床诊断结果为准。</p>
	
	
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
          imageUrl: require("../assets/cataract_001.png"),
          options: [{
          value: '选项1',
          label: 'ResNet18'
        }, {
          value: '选项2',
          label: '双皮奶'
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        value: ''
        }
      }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
