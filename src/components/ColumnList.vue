<template>
  <div class="row">
    <div v-for="item in columList" :key="item.id" class="col-4 mb-4">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
          <img
            :src="item.avatar"
            class="rounded-circle border border-light w-25 my-3"
            :alt="item.title"
          />
          <h5 class="card-title">{{ item.title }}</h5>
          <p class="card-text text-left">{{ item.description }}</p>
          <a href="#" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue';
export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
export default defineComponent({
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup(props) {
    const columList = computed(() => {
      return props.list.map(column => {
        if (!column.avatar) {
          column.avatar = require('@/assets/column.jpg');
        }
        return column;
      });
    });
    return { columList };
  }
});
</script>

<style scoped></style>
