<template>
  <NavBar
    :changeComponent="changeComponent"
    :currentComponent="currentComponent"
  />
  <component :is="components[currentComponent]"></component>
</template>

<script setup>
import { onMounted, ref } from "vue";
import NavBar from "@/components/NavBar.vue";
import AppTable from "@/components/AppTable.vue";
import Info from "@/components/Info.vue";

const currentComponent = ref("AppTable");
const components = {
  AppTable,
  Info,
};

function changeComponent(name) {
  currentComponent.value = name;
}
</script>
