<script setup>
import { ref } from 'vue'
import Checkbox from '@/components/Checkbox/Checkbox.vue'
import CheckboxGroup from '@/components/Checkbox/CheckboxGroup.vue'

const checkboxActive = ref(true)
const checkboxDisabled = ref(true)
const checkboxDisabledChecked = ref(true)

const listOfHeroes = ref([
  { name: 'Spider Man', id: 'h1' },
  { name: 'Batman', id: 'h2' },
  { name: 'Tor', id: 'h3' },
  { name: 'Loki', id: 'h4' },
])
const selectedHeroes = ref(['h1', 'h3'])
const switchProfessional = ref(false)
</script>

<template>
  <h1 class="heading-1">Checkbox</h1>
  <h2 class="heading-2">Checkbox Active</h2>
  <div class="line">
    <Checkbox
      label="Checkbox Active"
      id="checkboxActive"
      name="checkboxActive"
      value="Test"
      v-model:checked="checkboxActive"
    />
  </div>
  <h2 class="heading-2">Checkbox Disabled</h2>
  <div class="line">
    <Checkbox
      label="Checkbox Disabled"
      id="checkboxDisabled"
      name="checkboxDisabled"
      value="Test"
      v-model:checked="checkboxDisabledChecked"
      :disabled="checkboxDisabled"
    />
  </div>
  <h2 class="heading-2">Checkbox Group</h2>
  <div class="line line_block">
    <p>Selected Heroes: {{ selectedHeroes }}</p>
    <CheckboxGroup v-model:value="selectedHeroes" name="heroes" :options="listOfHeroes" />
  </div>
  <h2 class="heading-2">Switch</h2>
  <div class="line line_block">
    <p>Switch: {{ switchProfessional }}</p>
    <Checkbox
      type="switch"
      label="Switch"
      id="switch"
      name="switch"
      value="Switch"
      v-model:checked="switchProfessional"
    />
  </div>
</template>
