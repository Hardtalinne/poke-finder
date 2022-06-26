<script setup>
const props = defineProps({ modelValue: String })
const emit = defineEmits(['update:modelValue'])

// To serve as the instance of the <input> element `ref`.
const selectElement = $ref(null)

function updateModelValue() {
  emit('update:modelValue', selectElement.value)
}
</script>

<template>
  <div class="relative">
    <select
      ref="selectElement"
      :value="props.modelValue"
      @change="updateModelValue"
      class="h-10 px-2 py-1.5 rounded-sm font-normal text-base placeholder:text-neutral-400 bg-white/70 border border-black/5 outline outline-2 outline-offset-1 outline-transparent focus-visible:outline-black hover:bg-neutral-100/70 transition-all"
    >
      <option value="">Ordenar por</option>
      <option value="crescent">Ordem crescente</option>
      <option value="decrescent">Ordem decrescente</option>
      <option value="name">Ordem alfabética</option>
    </select>
  </div>
</template>
