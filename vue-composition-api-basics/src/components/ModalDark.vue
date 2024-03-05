<template>
      <teleport to=".modals-container">
        <div
          v-if="modelValue"
          class="modal-dark"
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

/*
  handleButtonClick 
*/
/*
const handleButtonClick = () => {
  emits('update:modelValue', false)
}
*/
</script>

<!--
<script>
export default{
    emits:['hideModal']
    props:{
        title:{
            type:String,
            default: 'No title specified'
        }
    }
}
</script>
-->
<style>

.modal-dark{
    background:#333;
    color:white;
    padding:10px;
    position:absolute;
    left: 0;
    top:0;
    width: 100%;
    height: 100%;
    z-index: 1;
}

</style>