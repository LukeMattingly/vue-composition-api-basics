<template>
      <teleport to=".modals-container">
        <div
          v-if="modelValue"
          class="modal"
        >
          <h1>{{ title }}</h1>
          <slot/>
          <button @click="emits('update:modelValue', false)" >Hide modal</button> 
        </div>
      </teleport>
</template>

<script setup>
/*
  props
*/
const props = defineProps({
  modelValue:{
    type: Boolean,
    default: false,
  },
  title: {
    type: String,
    default: 'No title specified'
  }
})

/*
  emits
*/
const emits = defineEmits(['update:modelValue'])


</script>

<style>

.modal{
    background:beige;
    color:black;
    padding:10px;
    position:absolute;
    left: 0;
    top:0;
    width: 100%;
    height: 100%;
    z-index: 1;
}

</style>