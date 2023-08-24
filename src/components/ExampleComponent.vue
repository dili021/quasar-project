<template>
  <div>
    <input
      type="search"
      autocapitalize="off"
      autocorrect="off"
      spellcheck="false"
    />
    <br />
    <br />
    <br />
    <q-input :model-value="text2" type="search" label="predictive" />
     <br />
    <br />
    <br />
    <textarea
      autocorrect="off"
      type="search"
      spellcheck="false"
      placeholder="abc"
      role="combobox"
    ></textarea>
     <br />
    <br />
    <br />
    <input type="text" aria-label="keywords" data-hj-allow="" autocorrect="off" autocapitalize="none" id="keywords" value="" name="keywords" placeholder="Praktično sve... (5.445.705 oglasa) " maxlength="100" autocomplete="off" style="padding-right: 150px;">
     <br />
    <br />
    <br />
    <input aria-autocomplete="none" aria-label="Search query" aria-owns="typeaheadDropdown-1" autocapitalize="sentences" autocomplete="off" autocorrect="off" placeholder="Search" role="combobox" spellcheck="false" enterkeyhint="search" type="text" dir="auto"  value="">
  </div>
</template>

<script setup lang="ts">
import { VNodeRef, computed, ref } from 'vue';
import { Todo, Meta } from './models';
const text = ref('');
const text2 = ref('');
const test = ref<VNodeRef>();
const onClick = () => {
  console.log(test.value);
};
interface Props {
  title: string;
  todos?: Todo[];
  meta: Meta;
  active: boolean;
}
const props = withDefaults(defineProps<Props>(), {
  todos: () => [],
});

const clickCount = ref(0);
function increment() {
  clickCount.value += 1;
  return clickCount.value;
}

const todoCount = computed(() => props.todos.length);
</script>
<style>

</style>
