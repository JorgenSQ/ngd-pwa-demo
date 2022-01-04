<template>
  <nav bg="bluegray-800" px-8>
    <div flex items-center justify-between h-20>
      <div flex items-center>
        <div ml-10 flex items-baseline space-x-4>
          <NuxtLink to="/" text="gray-300 lg" hover="bg-gray-700 text-white" p="x-3 y-2" rounded-md font-medium no-underline>Home</NuxtLink>
          <Dropdown v-model="selectedFacility" :options="facilities" optionLabel="name" optionValue="code" placeholder="Velg et anlegg" />
        </div>
      </div>
      <div ml-4 flex items-center md:ml-6>
        <NuxtLink to="/user" text="gray-300 lg" hover="bg-gray-700 text-white" p="x-3 y-2" rounded-md font-medium no-underline>User</NuxtLink>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";

const selectedFacility = ref("ng_2");
const facilities = ref([
  { name: "Facility 1", code: "ng_1" },
  { name: "Facility 2", code: "ng_2" },
  { name: "Facility 3", code: "ng_3" },
  { name: "Facility 4", code: "ng_4" },
]);
</script>

<style>
a.router-link-exact-active {
  background-color: var(--gray-900);
  color: white;
}

a.router-link-exact-active:hover {
  background-color: var(--gray-900);
}
</style>