<template>
  <span class="text-red-500">
    バックエンドからのデータ: {{ test }}
  </span>
</template>

<script lang="ts" setup>
import { onBeforeMount, ref } from 'vue';
import axios from 'axios';

const test = ref('')

onBeforeMount(async () => {
  const { data } = await axios.get('http://127.0.0.1:80/api/test')
  test.value = data.test
})
</script>