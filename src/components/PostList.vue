<template>
  <a-list item-layout="horizontal" :data-source="props.postList">
    <template #renderItem="{ item }">
      <a-list-item-meta>
        <template #description>
          <span v-html="item.highlight?.content || item.content"></span>
        </template>
        <template #title>
          <a href="https://www.antdv.com/"
            ><span v-html="item.highlight?.title || item.title"></span
          ></a>
        </template>
        <template #avatar>
          <a-avatar :src="gege" />
        </template>
      </a-list-item-meta>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import gege from "../assets/gege.jpg";
import { withDefaults, defineProps } from "vue";

interface Props {
  postList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  postList: () => [],
});
</script>

<style scoped>
.gege {
  width: 200px;
}
</style>
