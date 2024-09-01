<template>
  <div class="border-b border-gray-200 dark:border-neutral-700">
    <nav
      class="flex gap-x-1"
      aria-label="Tabs"
      role="tablist"
      aria-orientation="horizontal"
    >
      <button
        type="button"
        class="hs-tab-active:font-semibold hs-tab-active:border-blue-600 hs-tab-active:text-blue-600 py-4 px-1 inline-flex items-center gap-x-2 border-b-2 border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 focus:outline-none focus:text-blue-600 disabled:opacity-50 disabled:pointer-events-none dark:text-neutral-400 dark:hover:text-blue-500"
        :class="currentTab === 'List' ? 'active' : ''"
        id="tabs-with-underline-item-1"
        :aria-selected="currentTab === 'List' ? 'true' : 'false'"
        data-hs-tab="#tabs-with-underline-1"
        aria-controls="tabs-with-underline-1"
        role="tab"
        @click="changeTab('List')"
      >
        List
      </button>
      <button
        type="button"
        class="hs-tab-active:font-semibold hs-tab-active:border-blue-600 hs-tab-active:text-blue-600 py-4 px-1 inline-flex items-center gap-x-2 border-b-2 border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 focus:outline-none focus:text-blue-600 disabled:opacity-50 disabled:pointer-events-none dark:text-neutral-400 dark:hover:text-blue-500"
        :class="currentTab === 'Form' ? 'active' : ''"
        id="tabs-with-underline-item-2"
        :aria-selected="currentTab === 'Form' ? 'true' : 'false'"
        data-hs-tab="#tabs-with-underline-2"
        aria-controls="tabs-with-underline-2"
        role="tab"
        @click="changeTab('Form')"
      >
        Form
      </button>
    </nav>
  </div>

  <div class="mt-3">
    <div
      id="tabs-with-underline-1"
      role="tabpanel"
      :class="currentTab === 'List' ? '' : 'hidden'"
      aria-labelledby="tabs-with-underline-item-1"
    >
      <List />
    </div>
    <div
      id="tabs-with-underline-2"
      :class="currentTab === 'Form' ? '' : 'hidden'"
      role="tabpanel"
      aria-labelledby="tabs-with-underline-item-2"
    >
      <Form />
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import List from "./List.vue";
import Form from "./Form.vue";

const currentTab = ref("List");
function changeTab(name) {
  currentTab.value = name;
}
</script>
