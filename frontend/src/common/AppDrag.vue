<template>
    <div 
      :draggable="true"
      @dragstart.self="onDrag"
      @dragover.prevent
      @dragenter.prevent
    >
      <slot />
    </div>
  </template>
  
  <script setup>
  import { DATA_TRANSFER_PAYLOAD, MOVE } from "../constants.js";
  
  const props = defineProps({
    transferData: {
      type: Object,
      required: true,
    }
  });
  
  function onDrag(event) {
    const { dataTransfer } = event;
    if (!dataTransfer) return;
  
    dataTransfer.effectAllowed = MOVE;
    dataTransfer.dropEffect = MOVE;
    dataTransfer.setData(
      DATA_TRANSFER_PAYLOAD,
      JSON.stringify(props.transferData)
    );
  }
  </script>
  
  <style>

  </style>
  