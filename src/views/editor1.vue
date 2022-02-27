<template>
<div>
  <Editor :value="value"/>
    <Viewer class="viewer" :tabindex="2" :value="value"
    ></Viewer>
</div>
</template>

<script lang="ts">
import { computed, defineComponent, reactive, ref } from 'vue';

import 'bytemd/dist/index.min.css'
import { Editor,Viewer } from '@bytemd/vue'
import gfm from '@bytemd/plugin-gfm'
import highlight from "@bytemd/plugin-highlight-ssr";

const pluginsArr = [
  //将所有的扩展功能放入插件数组中，然后就可以生效了    
  gfm(),
  highlight(),
]

export default defineComponent({
  name: 'User',
  components: { Editor,Viewer },
  setup() {
    const plugins = pluginsArr;
    const value = computed(() => '');
    console.log(plugins, value.value)
    return { plugins, value};
  }
});
</script>