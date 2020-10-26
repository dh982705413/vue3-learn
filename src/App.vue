<template>
  <div class="container">
    <global-hearder :user="currentUser"></global-hearder>
    <column-list :list="list" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import 'bootstrap/dist/css/bootstrap.min.css';
import ColumnList, { ColumnProps } from '@/components/ColumnList.vue';
import GlobalHearder, { UserProps } from '@/components/GlobalHearder.vue';
const currentUser: UserProps = {
  isLogin: true,
  name: 'dh'
};
const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1专栏',
    avatar:
      'https://dss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1593106255,4245861836&fm=26&gp=0.jpg',
    description: 'test1'
  },
  {
    id: 2,
    title: 'test2专栏',
    avatar:
      'https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=151472226,3497652000&fm=26&gp=0.jpg',
    description: 'test2'
  },
  {
    id: 2,
    title: 'test2专栏',
    avatar:
      'https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=151472226,3497652000&fm=26&gp=0.jpg',
    description: 'test2'
  },
  {
    id: 2,
    title: 'test2专栏',
    avatar: '',
    description: 'test2'
  }
];
export default defineComponent({
  name: 'App',
  components: {
    ColumnList,
    GlobalHearder
  },
  setup() {
    return { list: testData, currentUser };
  }
});
</script>

<style></style>
