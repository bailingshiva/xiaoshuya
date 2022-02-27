<template>
 <mavon-editor
   v-model="data.content"
   ref="md"
   @imgAdd="$imgAdd"
   @change="change"
   style="min-height: 600px"
 />
</template>

<script lang="ts">
import { computed, defineComponent, reactive, ref } from 'vue';
import { mavonEditor } from "mavon-editor";
import "mavon-editor/dist/css/index.css";

export default defineComponent({
  components: {
    mavonEditor
  },
 setup() {
  const data = reactive({ content: '' });
  return {data}
 },
  methods: {
    // 将图片上传到服务器，返回地址替换到md中
    $imgAdd(pos, $file) {
      // var formdata = new FormData();
      // formdata.append("file", $file);
      // //将下面上传接口替换为你自己的服务器接口
      // axios({
      //   url: "/common/upload",
      //   method: "post",
      //   data: formdata,
      //   headers: { "Content-Type": "multipart/form-data" }
      // }).then(url => {
      //   this.$refs.md.$img2Url(pos, url);
      // });
    },
    change(value, render) {
      // // render 为 markdown 解析后的结果
      // this.html = render;
    }
    }
})
</script>