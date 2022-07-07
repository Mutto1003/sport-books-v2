<template>
  <a-layout-header style="background: #fff; padding: 0">
    <RightCircleFilled
      :style="{ fontSize: '20px', color: '#696CFF' }"
      v-if="collapsed"
      class="trigger"
      @click="toggleCollapse"
    />
    <LeftCircleFilled
      :style="{ fontSize: '20px', color: '#696CFF' }"
      v-else
      class="trigger"
      @click="toggleCollapse"
    />
  </a-layout-header>
</template>

<script lang="ts">
import { LeftCircleFilled, RightCircleFilled } from "@ant-design/icons-vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  components: {
    LeftCircleFilled,
    RightCircleFilled,
  },
  props: ["collapsed"],
  setup(props, { emit }) {
    const toggleCollapse = () => {
      emit("update:collapsed", !props.collapsed);
    };
    return { toggleCollapse };
  },
});
</script>

<style scoped>
@import "@/css/styles.css";
</style>
