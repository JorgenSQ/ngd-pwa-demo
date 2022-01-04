<template>
  <h2 text-center>Week 50 waste forecast reporting</h2>

  <div flex flex-col justify-center>
    <div v-for="(reg, index) in registeredMaterials" :key="index" flex justify-end my-2 space-x-2>
      <Dropdown flex-grow v-model="reg.materialCode" :options="materials" optionLabel="materialText" optionValue="materialCode" scrollHeight="256" placeholder="Material" />
      <InputNumber v-model="reg.loads" :min="1" :max="99" w-12 text-center showButtons buttonLayout="horizontal" incrementButtonIcon="pi pi-plus" decrementButtonIcon="pi pi-minus" />
      <Button icon="pi pi-comment" />
      <Button @click="removeEntry(index)" icon="pi pi-times" class="p-button-danger" />
    </div>
    <div flex flex-auto justify-bewteen space-x-2 my-4>
      <Button flex-grow @click="newEntry" label="New row"></Button>
      <Button flex-grow class="p-button-success" label="Submit"></Button>
    </div>
  </div>

</template>

<script setup lang="ts">
//import { useMouse } from "@vueuse/nuxt/node_modules/@vueuse/core";
import { ref } from "vue";

const materials = ref([
  { materialCode: "metal", materialText: "Metal" },
  { materialCode: "glass", materialText: "Glass" },
  { materialCode: "paper", materialText: "Paper" },
  { materialCode: "cardboard", materialText: "Cardboard" },
  { materialCode: "wood", materialText: "Wood" },
]);

const registeredMaterials = ref([
  { materialCode: "glass", loads: 22, comment: "" },
  { materialCode: "metal", loads: 5, comment: "" },
  { materialCode: "cardboard", loads: 3, comment: "" },
]);

const newEntry = () => {
  registeredMaterials.value.push({ materialCode: "", loads: 1, comment: "" });
};

const removeEntry = (index: number) => {
  console.log(index);
  registeredMaterials.value = registeredMaterials.value.splice(index, 1);
};
</script>